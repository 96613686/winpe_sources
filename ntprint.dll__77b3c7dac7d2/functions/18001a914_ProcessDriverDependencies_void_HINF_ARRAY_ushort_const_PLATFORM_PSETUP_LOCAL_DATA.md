# ProcessDriverDependencies(void *,_HINF_ARRAY *,ushort const *,PLATFORM,_PSETUP_LOCAL_DATA *)

- ea: `0x18001a914`
- end: `0x18001af9f`
- name: `?ProcessDriverDependencies@@YAHPEAXPEAU_HINF_ARRAY@@PEBGW4PLATFORM@@PEAU_PSETUP_LOCAL_DATA@@@Z`
- size: `1675`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `installer_update`

## callers

- `0x1800217e0`

## callees

- `0x180002300`
- `0x180002f48`
- `0x18000d57c`
- `0x18000d624`
- `0x18001825c`
- `0x18001a10c`
- `0x18001a1d8`
- `0x18001a914`
- `0x18001c978`
- `0x18001d93c`
- `0x18001eed8`
- `0x18001f1a4`
- `0x180034f60`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001ab88`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001ab88`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a9f4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001aa41`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001aa49`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001aad9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001aae1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001aba0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ac15`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ac1d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001acd4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001acdc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001acfe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ad06`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001adc4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001adcc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ae31`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a9f4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001aa41`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001aa49`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001aad9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001aae1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001aba0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ac15`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ac1d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001acd4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001acdc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001acfe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ad06`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001adc4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001adcc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ae31`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001aef0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001aef0`
- `SETUPAPI!SetupFindFirstLineW` at `0x18001aa21`
- `SETUPAPI!SetupFindFirstLineW` at `0x18001aaaf`
- `SETUPAPI!SetupFindFirstLineW` at `0x18001ac82`
- `SETUPAPI!SetupFindFirstLineW` at `0x18001aa21`
- `SETUPAPI!SetupFindFirstLineW` at `0x18001aaaf`
- `SETUPAPI!SetupFindFirstLineW` at `0x18001ac82`

## string_xrefs

- `0x18001ae83`: `Invalid Argument: hInf=%p, phInfArray=%p, pszInstallSection=%ws, pLocalData=%p`
- `0x18001ab74`: `No core printer drivers for the given platform are installed.`
- `0x18001ad0c`: `Error retrieving the specific core drivers that the driver to be installed depends upon: %d`
- `0x18001add2`: `Error opening core driver INF files: %d`
- `0x18001ae04`: `OpenCoreDriverInfs failed`

## pseudocode

```c
__int64 __fastcall ProcessDriverDependencies(void *a1, struct _HINF_ARRAY *a2, const WCHAR *a3, int a4, __int64 a5)
{
  __int64 v6; // r13
  signed int v7; // ebx
  unsigned int LatestCoreDrivers; // esi
  __int64 v10; // rdx
  int ActualPackageSection; // r14d
  signed int v12; // eax
  WCHAR *v13; // r9
  const unsigned __int16 *v14; // r8
  DWORD v15; // eax
  unsigned int v16; // ecx
  DWORD v17; // eax
  unsigned int v18; // ecx
  unsigned __int16 *v19; // rcx
  unsigned int v20; // ecx
  const unsigned __int16 *v21; // rax
  DWORD v22; // eax
  unsigned int v23; // ecx
  DWORD v24; // eax
  unsigned int v25; // ecx
  DWORD LastError; // eax
  unsigned __int16 *v27; // rcx
  unsigned __int16 *v29; // [rsp+28h] [rbp-B9h]
  unsigned __int16 *v30; // [rsp+30h] [rbp-B1h]
  unsigned __int16 *v31; // [rsp+38h] [rbp-A9h]
  unsigned int v32; // [rsp+40h] [rbp-A1h]
  unsigned int v33; // [rsp+48h] [rbp-99h]
  int IsPackageAware; // [rsp+60h] [rbp-81h]
  struct _INFCONTEXT Context; // [rsp+68h] [rbp-79h] BYREF
  struct _HINF_ARRAY *v37; // [rsp+80h] [rbp-61h]
  WCHAR Section[40]; // [rsp+90h] [rbp-51h] BYREF

  v6 = a4;
  v7 = 0;
  v37 = a2;
  memset(&Context, 0, sizeof(Context));
  if ( a1 == (void *)-1LL || !a2 || !a3 || !a5 )
  {
    LatestCoreDrivers = 0;
    ClassInstallerTelemetry::WriteDbgTraceError(
      "ProcessDriverDependencies",
      L"Invalid Argument: hInf=%p, phInfArray=%p, pszInstallSection=%ws, pLocalData=%p",
      a1,
      a2,
      a3,
      a5);
    if ( a5 )
    {
      v21 = *(const unsigned __int16 **)a5;
      v27 = *(unsigned __int16 **)(a5 + 8);
    }
    else
    {
      v21 = 0;
      v27 = 0;
    }
    v33 = -2147024809;
    v14 = L"Invalid argument(s)";
    v32 = 87;
    v31 = (unsigned __int16 *)PlatformEnv[v6];
    v30 = (unsigned __int16 *)a3;
    v29 = v27;
    v13 = 0;
    goto LABEL_33;
  }
  ClassInstallerTelemetry::WriteDbgTraceInfo(
    "ProcessDriverDependencies",
    L"Gathering required core printer driver INF handles");
  IsPackageAware = InfIsPackageAware(a1);
  if ( IsPackageAware < 0 )
  {
    LatestCoreDrivers = 0;
    LastError = GetLastError();
    v33 = IsPackageAware;
    v14 = L"InfIsPackageAware failed";
    v32 = LastError;
    v13 = 0;
    v31 = (unsigned __int16 *)PlatformEnv[v6];
    v30 = (unsigned __int16 *)a3;
    goto LABEL_32;
  }
  LatestCoreDrivers = 1;
  if ( !*(_DWORD *)(a5 + 172) )
    goto LABEL_22;
  memset_0(Section, 0, sizeof(Section));
  ActualPackageSection = GetActualPackageSection((unsigned int)v6, v10, Section);
  if ( ActualPackageSection >= 0 )
  {
    if ( SetupFindFirstLineW(a1, Section, L"CoreDriverDependencies", &Context) && (int)InfGetMultiSz(&Context) < 0 )
    {
      LatestCoreDrivers = 0;
      v7 = GetLastError();
      v15 = GetLastError();
      ClassInstallerTelemetry::WriteDbgTraceError(
        "ProcessDriverDependencies",
        L"Error getting INF field %ws: %d",
        L"CoreDriverDependencies",
        v15);
      if ( v7 > 0 )
        v16 = (unsigned __int16)v7 | 0x80070000;
      else
        v16 = v7;
      v33 = v16;
      v14 = L"InfGetMultiSz for CoreDriverDependencies failed";
      v32 = v7;
      v13 = 0;
      goto LABEL_31;
    }
    if ( *(_QWORD *)(a5 + 224) )
    {
      if ( SetupFindFirstLineW(a1, Section, L"InboxVersionRequired", &Context) )
      {
        LatestCoreDrivers = ObtainRequiredInboxVersion(
                              a1,
                              &Context,
                              (struct _FILETIME *)(a5 + 240),
                              (unsigned __int64 *)(a5 + 248));
        if ( !LatestCoreDrivers )
        {
          v7 = GetLastError();
          v17 = GetLastError();
          ClassInstallerTelemetry::WriteDbgTraceError(
            "ProcessDriverDependencies",
            L"Error retrieving required inbox core driver version field: %d",
            v17);
          if ( v7 > 0 )
            v18 = (unsigned __int16)v7 | 0x80070000;
          else
            v18 = v7;
          v33 = v18;
          v14 = L"ObtainRequiredInboxVersion failed";
          v32 = v7;
          v13 = 0;
          goto LABEL_31;
        }
      }
    }
LABEL_22:
    v19 = *(unsigned __int16 **)(a5 + 224);
    if ( v19 )
    {
      LatestCoreDrivers = FindLatestCoreDrivers(
                            v19,
                            v6,
                            *(FILETIME *)(a5 + 240),
                            *(_QWORD *)(a5 + 248),
                            0,
                            (_QWORD *)(a5 + 408),
                            (unsigned int *)(a5 + 400));
      if ( !LatestCoreDrivers )
      {
        if ( MyPlatform != (_DWORD)v6 )
        {
          ClassInstallerTelemetry::WriteDbgTraceError(
            "ProcessDriverDependencies",
            L"No core printer drivers for the given platform are installed.");
          SetLastError(0x661u);
        }
        ClassInstallerTelemetry::WriteDbgTraceError(
          "ProcessDriverDependencies",
          L"Error finding core driver packages: %d",
          0);
        v12 = GetLastError();
        v7 = v12;
        if ( v12 > 0 )
          v20 = (unsigned __int16)v12 | 0x80070000;
        else
          v20 = v12;
        v33 = v20;
        v14 = L"FindLatestCoreDrivers failed";
        v13 = 0;
        goto LABEL_30;
      }
      if ( !*(_DWORD *)(a5 + 400) )
      {
        LatestCoreDrivers = 0;
        v7 = GetLastError();
        v22 = GetLastError();
        ClassInstallerTelemetry::WriteDbgTraceError(
          "ProcessDriverDependencies",
          L"No core driver dependencies found: %d",
          v22);
        if ( v7 > 0 )
          v23 = (unsigned __int16)v7 | 0x80070000;
        else
          v23 = v7;
        v33 = v23;
        v14 = L"No core drivers in code dependencies";
        v32 = v7;
        v13 = 0;
        goto LABEL_31;
      }
    }
    if ( *(_QWORD *)(a5 + 224) && SetupFindFirstLineW(a1, a3, L"CoreDriverSections", &Context) )
    {
      if ( (int)InfGetMultiSz(&Context) < 0 )
      {
        LatestCoreDrivers = 0;
        v7 = GetLastError();
        v24 = GetLastError();
        ClassInstallerTelemetry::WriteDbgTraceError(
          "ProcessDriverDependencies",
          L"Error retrieving the specific core drivers that the driver to be installed depends upon: %d",
          v24);
        if ( v7 > 0 )
          v25 = (unsigned __int16)v7 | 0x80070000;
        else
          v25 = v7;
        v33 = v25;
        v14 = L"InfGetMultiSz for core driver sections failed";
        v32 = v7;
        v13 = 0;
        v31 = (unsigned __int16 *)PlatformEnv[v6];
        v30 = (unsigned __int16 *)a3;
        goto LABEL_32;
      }
      LatestCoreDrivers = 1;
    }
    ClassInstallerTelemetry::WriteDbgTraceInfo(
      "ProcessDriverDependencies",
      L"Successfully processed core driver dependencies");
    SplLogPrinterSetupEvent(
      &SETUP_PARSEINF_SUCCEEDED,
      L"ProcessDriverDependencies",
      0,
      0,
      *(const unsigned __int16 **)a5,
      *(const unsigned __int16 **)(a5 + 8),
      a3,
      (const unsigned __int16 *)PlatformEnv[v6],
      0,
      0);
    return LatestCoreDrivers;
  }
  LatestCoreDrivers = 0;
  v12 = GetLastError();
  v13 = Section;
  v33 = ActualPackageSection;
  v14 = L"GetActualPackageSection failed (actual section name, if any, in addditional info)";
LABEL_30:
  v32 = v12;
LABEL_31:
  v31 = (unsigned __int16 *)PlatformEnv[v6];
  v30 = (unsigned __int16 *)a3;
LABEL_32:
  v29 = *(unsigned __int16 **)(a5 + 8);
  v21 = *(const unsigned __int16 **)a5;
LABEL_33:
  SplLogPrinterSetupEvent(&SETUP_PARSEINF_FAILED, L"ProcessDriverDependencies", v14, v13, v21, v29, v30, v31, v32, v33);
  ClassInstallerTelemetry::WriteDbgTraceError(
    "ProcessDriverDependencies",
    L"Error processing core driver dependencies: %d",
    (unsigned int)v7);
  return LatestCoreDrivers;
}

```

## disassembly

```asm
0x18001a914  push    rbp
0x18001a916  push    rbx
0x18001a917  push    rsi
0x18001a918  push    rdi
0x18001a919  push    r12
0x18001a91b  push    r13
0x18001a91d  push    r14
0x18001a91f  push    r15
0x18001a921  lea     rbp, [rsp-17h]
0x18001a926  sub     rsp, 0F8h
0x18001a92d  mov     rax, cs:__security_cookie
0x18001a934  xor     rax, rsp
0x18001a937  mov     [rbp+4Fh+var_50], rax
0x18001a93b  mov     rdi, [rbp+4Fh+arg_20]
0x18001a93f  mov     r12, rcx
0x18001a942  xor     ecx, ecx
0x18001a944  movsxd  r13, r9d
0x18001a947  xor     ebx, ebx
0x18001a949  mov     [rsp+130h+var_E0], r8
0x18001a94e  mov     [rbp+4Fh+var_B0], rdx
0x18001a952  xorps   xmm0, xmm0
0x18001a955  mov     qword ptr [rbp+4Fh+Context.Section], rcx
0x18001a959  mov     r14, r8
0x18001a95c  mov     [rsp+130h+hMem], rcx
0x18001a961  mov     rax, rdx
0x18001a964  movups  xmmword ptr [rbp+4Fh+Context.Inf], xmm0
0x18001a968  cmp     r12, 0FFFFFFFFFFFFFFFFh
0x18001a96c  jz      loc_18001AE6C
0x18001a972  test    rax, rax
0x18001a975  jz      loc_18001AE6C
0x18001a97b  test    r8, r8
0x18001a97e  jz      loc_18001AE6C
0x18001a984  test    rdi, rdi
0x18001a987  jz      loc_18001AE6C
0x18001a98d  lea     r15, aProcessdriverd_1; "ProcessDriverDependencies"
0x18001a994  mov     rcx, r15; char *
0x18001a997  lea     rdx, aGatheringRequi; "Gathering required core printer driver "...
0x18001a99e  call    ?WriteDbgTraceInfo@ClassInstallerTelemetry@@SAXPEADPEAGZZ; ClassInstallerTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x18001a9a3  lea     r14, [rdi+0ACh]
0x18001a9aa  mov     edx, r13d
0x18001a9ad  mov     r8, r14
0x18001a9b0  mov     rcx, r12; InfHandle
0x18001a9b3  call    InfIsPackageAware
0x18001a9b8  mov     [rsp+130h+var_D0], eax
0x18001a9bc  test    eax, eax
0x18001a9be  js      loc_18001AE2F
0x18001a9c4  lea     esi, [rbx+1]
0x18001a9c7  cmp     [r14], ebx
0x18001a9ca  jz      loc_18001AB21
0x18001a9d0  xor     edx, edx; Val
0x18001a9d2  lea     r8d, [rbx+50h]; Size
0x18001a9d6  lea     rcx, [rbp+4Fh+Section]; void *
0x18001a9da  call    memset_0
0x18001a9df  lea     r8, [rbp+4Fh+Section]
0x18001a9e3  mov     ecx, r13d
0x18001a9e6  call    GetActualPackageSection
0x18001a9eb  mov     r14d, eax
0x18001a9ee  test    eax, eax
0x18001a9f0  jns     short loc_18001AA0F
0x18001a9f2  xor     esi, esi
0x18001a9f4  call    cs:__imp_GetLastError
0x18001a9fa  lea     r9, [rbp+4Fh+Section]
0x18001a9fe  mov     [rsp+130h+var_E8], r14d
0x18001aa03  lea     r8, aGetactualpacka_1; "GetActualPackageSection failed (actual "...
0x18001aa0a  jmp     loc_18001ABC7
0x18001aa0f  lea     r9, [rbp+4Fh+Context]; Context
0x18001aa13  mov     rcx, r12; InfHandle
0x18001aa16  lea     r8, aCoredriverdepe; "CoreDriverDependencies"
0x18001aa1d  lea     rdx, [rbp+4Fh+Section]; Section
0x18001aa21  call    cs:__imp_SetupFindFirstLineW
0x18001aa27  test    eax, eax
0x18001aa29  jz      short loc_18001AA90
0x18001aa2b  lea     r8, [rdi+0E0h]
0x18001aa32  lea     rcx, [rbp+4Fh+Context]; Context
0x18001aa36  call    InfGetMultiSz
0x18001aa3b  test    eax, eax
0x18001aa3d  jns     short loc_18001AA90
0x18001aa3f  xor     esi, esi
0x18001aa41  call    cs:__imp_GetLastError
0x18001aa47  mov     ebx, eax
0x18001aa49  call    cs:__imp_GetLastError
0x18001aa4f  lea     r8, aCoredriverdepe; "CoreDriverDependencies"
0x18001aa56  mov     rcx, r15; char *
0x18001aa59  mov     r9d, eax
0x18001aa5c  lea     rdx, aErrorGettingIn; "Error getting INF field %ws: %d"
0x18001aa63  call    ?WriteDbgTraceError@ClassInstallerTelemetry@@SAXPEADPEAGZZ; ClassInstallerTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x18001aa68  test    ebx, ebx
0x18001aa6a  jg      short loc_18001AA70
0x18001aa6c  mov     ecx, ebx
0x18001aa6e  jmp     short loc_18001AA79
0x18001aa70  movzx   ecx, bx
0x18001aa73  or      ecx, 80070000h
0x18001aa79  mov     [rsp+130h+var_E8], ecx
0x18001aa7d  lea     r8, aInfgetmultiszF; "InfGetMultiSz for CoreDriverDependencie"...
0x18001aa84  mov     [rsp+130h+var_F0], ebx
0x18001aa88  xor     r9d, r9d
0x18001aa8b  jmp     loc_18001ABCB
0x18001aa90  cmp     [rdi+0E0h], rbx
0x18001aa97  jz      loc_18001AB21
0x18001aa9d  lea     r9, [rbp+4Fh+Context]; Context
0x18001aaa1  mov     rcx, r12; InfHandle
0x18001aaa4  lea     r8, cszInboxVersionRequired; "InboxVersionRequired"
0x18001aaab  lea     rdx, [rbp+4Fh+Section]; Section
0x18001aaaf  call    cs:__imp_SetupFindFirstLineW
0x18001aab5  test    eax, eax
0x18001aab7  jz      short loc_18001AB21
0x18001aab9  lea     r9, [rdi+0F8h]; unsigned __int64 *
0x18001aac0  mov     rcx, r12; InfHandle
0x18001aac3  lea     r8, [rdi+0F0h]; struct _FILETIME *
0x18001aaca  lea     rdx, [rbp+4Fh+Context]; struct _INFCONTEXT *
0x18001aace  call    ?ObtainRequiredInboxVersion@@YAHPEAXPEAU_INFCONTEXT@@PEAU_FILETIME@@PEA_K@Z; ObtainRequiredInboxVersion(void *,_INFCONTEXT *,_FILETIME *,unsigned __int64 *)
0x18001aad3  mov     esi, eax
0x18001aad5  test    eax, eax
0x18001aad7  jnz     short loc_18001AB21
0x18001aad9  call    cs:__imp_GetLastError
0x18001aadf  mov     ebx, eax
0x18001aae1  call    cs:__imp_GetLastError
0x18001aae7  lea     rdx, aErrorRetrievin_2; "Error retrieving required inbox core dr"...
0x18001aaee  mov     rcx, r15; char *
0x18001aaf1  mov     r8d, eax
0x18001aaf4  call    ?WriteDbgTraceError@ClassInstallerTelemetry@@SAXPEADPEAGZZ; ClassInstallerTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x18001aaf9  test    ebx, ebx
0x18001aafb  jg      short loc_18001AB01
0x18001aafd  mov     ecx, ebx
0x18001aaff  jmp     short loc_18001AB0A
0x18001ab01  movzx   ecx, bx
0x18001ab04  or      ecx, 80070000h
0x18001ab0a  mov     [rsp+130h+var_E8], ecx
0x18001ab0e  lea     r8, aObtainrequired; "ObtainRequiredInboxVersion failed"
0x18001ab15  mov     [rsp+130h+var_F0], ebx
0x18001ab19  xor     r9d, r9d
0x18001ab1c  jmp     loc_18001ABCB
0x18001ab21  mov     rcx, [rdi+0E0h]; unsigned __int16 *
0x18001ab28  lea     r14, [rdi+190h]
0x18001ab2f  test    rcx, rcx
0x18001ab32  jz      loc_18001AC5D
0x18001ab38  mov     r9, [rdi+0F8h]
0x18001ab3f  lea     rax, [r14+8]
0x18001ab43  mov     r8, [rdi+0F0h]
0x18001ab4a  mov     edx, r13d
0x18001ab4d  mov     [rsp+130h+var_100], r14; __int64
0x18001ab52  mov     [rsp+130h+var_108], rax; __int64
0x18001ab57  mov     [rsp+130h+var_110], rbx; __int64
0x18001ab5c  call    FindLatestCoreDrivers
0x18001ab61  mov     esi, eax
0x18001ab63  test    eax, eax
0x18001ab65  jnz     loc_18001AC0E
0x18001ab6b  cmp     cs:MyPlatform, r13d
0x18001ab72  jz      short loc_18001AB8E
0x18001ab74  lea     rdx, aNoCorePrinterD; "No core printer drivers for the given p"...
0x18001ab7b  mov     rcx, r15; char *
0x18001ab7e  call    ?WriteDbgTraceError@ClassInstallerTelemetry@@SAXPEADPEAGZZ; ClassInstallerTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x18001ab83  mov     ecx, 661h; dwErrCode
0x18001ab88  call    cs:__imp_SetLastError
0x18001ab8e  xor     r8d, r8d
0x18001ab91  lea     rdx, aErrorFindingCo_0; "Error finding core driver packages: %d"
0x18001ab98  mov     rcx, r15; char *
0x18001ab9b  call    ?WriteDbgTraceError@ClassInstallerTelemetry@@SAXPEADPEAGZZ; ClassInstallerTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x18001aba0  call    cs:__imp_GetLastError
0x18001aba6  mov     ebx, eax
0x18001aba8  test    eax, eax
0x18001abaa  jg      short loc_18001ABB0
0x18001abac  mov     ecx, eax
0x18001abae  jmp     short loc_18001ABB9
0x18001abb0  movzx   ecx, ax
0x18001abb3  or      ecx, 80070000h
0x18001abb9  mov     [rsp+130h+var_E8], ecx; unsigned int
0x18001abbd  lea     r8, aFindlatestcore; "FindLatestCoreDrivers failed"
0x18001abc4  xor     r9d, r9d; unsigned __int16 *
0x18001abc7  mov     [rsp+130h+var_F0], eax; unsigned int
0x18001abcb  mov     rdx, [rsp+130h+var_E0]
0x18001abd0  lea     r12, PlatformEnv
0x18001abd7  mov     rax, [r12+r13*8]
0x18001abdb  mov     [rsp+130h+var_F8], rax; unsigned __int16 *
0x18001abe0  mov     [rsp+130h+var_100], rdx; unsigned __int16 *
0x18001abe5  mov     rax, [rdi+8]
0x18001abe9  mov     [rsp+130h+var_108], rax; unsigned __int16 *
0x18001abee  mov     rax, [rdi]
0x18001abf1  lea     rdx, aProcessdriverd_0; "ProcessDriverDependencies"
0x18001abf8  mov     [rsp+130h+var_110], rax; unsigned __int16 *
0x18001abfd  lea     rcx, SETUP_PARSEINF_FAILED; struct _EVENT_DESCRIPTOR *
0x18001ac04  call    ?SplLogPrinterSetupEvent@@YAXPEBU_EVENT_DESCRIPTOR@@PEBG111111KK@Z; SplLogPrinterSetupEvent(_EVENT_DESCRIPTOR const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ulong,ulong)
0x18001ac09  jmp     loc_18001AEE6
0x18001ac0e  cmp     [r14], ebx
0x18001ac11  jnz     short loc_18001AC65
0x18001ac13  xor     esi, esi
0x18001ac15  call    cs:__imp_GetLastError
0x18001ac1b  mov     ebx, eax
0x18001ac1d  call    cs:__imp_GetLastError
0x18001ac23  lea     rdx, aNoCoreDriverDe; "No core driver dependencies found: %d"
0x18001ac2a  mov     rcx, r15; char *
0x18001ac2d  mov     r8d, eax
0x18001ac30  call    ?WriteDbgTraceError@ClassInstallerTelemetry@@SAXPEADPEAGZZ; ClassInstallerTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x18001ac35  test    ebx, ebx
0x18001ac37  jg      short loc_18001AC3D
0x18001ac39  mov     ecx, ebx
0x18001ac3b  jmp     short loc_18001AC46
0x18001ac3d  movzx   ecx, bx
0x18001ac40  or      ecx, 80070000h
0x18001ac46  mov     [rsp+130h+var_E8], ecx
0x18001ac4a  lea     r8, aNoCoreDriversI; "No core drivers in code dependencies"
0x18001ac51  mov     [rsp+130h+var_F0], ebx
0x18001ac55  xor     r9d, r9d
0x18001ac58  jmp     loc_18001ABCB
0x18001ac5d  test    esi, esi
0x18001ac5f  jz      loc_18001AEDF
0x18001ac65  cmp     qword ptr [rdi+0E0h], 0
0x18001ac6d  jz      short loc_18001ACA3
0x18001ac6f  mov     rdx, [rsp+130h+var_E0]; Section
0x18001ac74  lea     r9, [rbp+4Fh+Context]; Context
0x18001ac78  lea     r8, cszCoreDriverSections; "CoreDriverSections"
0x18001ac7f  mov     rcx, r12; InfHandle
0x18001ac82  call    cs:__imp_SetupFindFirstLineW
0x18001ac88  test    eax, eax
0x18001ac8a  jz      short loc_18001ACA3
0x18001ac8c  lea     r8, [rsp+130h+hMem]
0x18001ac91  lea     rcx, [rbp+4Fh+Context]; Context
0x18001ac95  call    InfGetMultiSz
0x18001ac9a  test    eax, eax
0x18001ac9c  js      short loc_18001ACFC
0x18001ac9e  mov     esi, 1
0x18001aca3  mov     rcx, [rsp+130h+hMem]; unsigned __int16 *
0x18001aca8  test    rcx, rcx
0x18001acab  jz      loc_18001AD9A
0x18001acb1  mov     r8d, [r14]; unsigned int
0x18001acb4  lea     rax, [r14+10h]
0x18001acb8  mov     rdx, [r14+8]; struct _CORE_DRIVER_INFO *
0x18001acbc  lea     r9, [r14+18h]; struct _CORE_SECTION_INFO **
0x18001acc0  mov     [rsp+130h+var_110], rax; unsigned int *
0x18001acc5  call    ?FindCoreDriverSections@@YAHPEBGPEAU_CORE_DRIVER_INFO@@KPEAPEAU_CORE_SECTION_INFO@@PEAK@Z; FindCoreDriverSections(ushort const *,_CORE_DRIVER_INFO *,ulong,_CORE_SECTION_INFO * *,ulong *)
0x18001acca  mov     esi, eax
0x18001accc  test    eax, eax
0x18001acce  jnz     loc_18001ADA2
0x18001acd4  call    cs:__imp_GetLastError
0x18001acda  mov     ebx, eax
0x18001acdc  call    cs:__imp_GetLastError
0x18001ace2  lea     rdx, aErrorFindingCo; "Error finding core driver sections: %d"
0x18001ace9  mov     rcx, r15; char *
0x18001acec  mov     r8d, eax
0x18001acef  call    ?WriteDbgTraceError@ClassInstallerTelemetry@@SAXPEADPEAGZZ; ClassInstallerTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x18001acf4  test    ebx, ebx
0x18001acf6  jg      short loc_18001AD60
0x18001acf8  mov     ecx, ebx
0x18001acfa  jmp     short loc_18001AD69
0x18001acfc  xor     esi, esi
0x18001acfe  call    cs:__imp_GetLastError
0x18001ad04  mov     ebx, eax
0x18001ad06  call    cs:__imp_GetLastError
0x18001ad0c  lea     rdx, aErrorRetrievin_15; "Error retrieving the specific core driv"...
0x18001ad13  mov     rcx, r15; char *
0x18001ad16  mov     r8d, eax
0x18001ad19  call    ?WriteDbgTraceError@ClassInstallerTelemetry@@SAXPEADPEAGZZ; ClassInstallerTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x18001ad1e  test    ebx, ebx
0x18001ad20  jg      short loc_18001AD26
0x18001ad22  mov     ecx, ebx
0x18001ad24  jmp     short loc_18001AD2F
0x18001ad26  movzx   ecx, bx
0x18001ad29  or      ecx, 80070000h
0x18001ad2f  mov     [rsp+130h+var_E8], ecx
0x18001ad33  lea     r12, PlatformEnv
0x18001ad3a  mov     rax, [r12+r13*8]
0x18001ad3e  lea     r8, aInfgetmultiszF_0; "InfGetMultiSz for core driver sections "...
0x18001ad45  mov     [rsp+130h+var_F0], ebx
0x18001ad49  xor     r9d, r9d
0x18001ad4c  mov     [rsp+130h+var_F8], rax
0x18001ad51  mov     rax, [rsp+130h+var_E0]
0x18001ad56  mov     [rsp+130h+var_100], rax
0x18001ad5b  jmp     loc_18001ABE5
0x18001ad60  movzx   ecx, bx
0x18001ad63  or      ecx, 80070000h
0x18001ad69  mov     [rsp+130h+var_E8], ecx
0x18001ad6d  lea     r12, PlatformEnv
0x18001ad74  mov     rax, [r12+r13*8]
0x18001ad78  lea     r8, aFindcoredriver; "FindCoreDriverSections failed"
0x18001ad7f  mov     [rsp+130h+var_F0], ebx
0x18001ad83  xor     r9d, r9d
0x18001ad86  mov     [rsp+130h+var_F8], rax
0x18001ad8b  mov     rax, [rsp+130h+var_E0]
0x18001ad90  mov     [rsp+130h+var_100], rax
0x18001ad95  jmp     loc_18001ABE5
0x18001ad9a  test    esi, esi
0x18001ad9c  jz      loc_18001AEDF
0x18001ada2  cmp     [rsp+130h+hMem], 0
0x18001ada8  jz      loc_18001AF37
0x18001adae  mov     rdx, [rbp+4Fh+var_B0]; struct _HINF_ARRAY *
0x18001adb2  mov     rcx, r14; struct _CORE_DEPENDENCIES *
0x18001adb5  call    ?OpenCoreDriverInfs@@YAHPEAU_CORE_DEPENDENCIES@@PEAU_HINF_ARRAY@@@Z; OpenCoreDriverInfs(_CORE_DEPENDENCIES *,_HINF_ARRAY *)
0x18001adba  mov     esi, eax
0x18001adbc  test    eax, eax
0x18001adbe  jnz     loc_18001AEDF
0x18001adc4  call    cs:__imp_GetLastError
0x18001adca  mov     ebx, eax
0x18001adcc  call    cs:__imp_GetLastError
0x18001add2  lea     rdx, aErrorOpeningCo; "Error opening core driver INF files: %d"
0x18001add9  mov     rcx, r15; char *
0x18001addc  mov     r8d, eax
0x18001addf  call    ?WriteDbgTraceError@ClassInstallerTelemetry@@SAXPEADPEAGZZ; ClassInstallerTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x18001ade4  test    ebx, ebx
0x18001ade6  jg      short loc_18001ADEC
0x18001ade8  mov     ecx, ebx
  ... truncated ...
```
