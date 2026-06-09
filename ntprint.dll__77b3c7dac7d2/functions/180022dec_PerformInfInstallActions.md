# PerformInfInstallActions

- ea: `0x180022dec`
- end: `0x18002330f`
- name: `PerformInfInstallActions`
- size: `1315`
- prototype: `__int64 __usercall@<rax>(HDEVINFO DeviceInfoSet@<rcx>, int, int)`
- caller_count: `2`
- callee_count: `14`
- tags: `file_ops, loader_planting, installer_update`

## callers

- `0x18000c408`
- `0x180013e68`

## callees

- `0x180002300`
- `0x180002f48`
- `0x18000b200`
- `0x18000d57c`
- `0x18000d624`
- `0x18000d904`
- `0x18001a454`
- `0x18001bcd4`
- `0x18001d8c8`
- `0x18001f958`
- `0x1800217e0`
- `0x180022dec`
- `0x180034bec`
- `0x180034f60`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022ede`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022fa1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800230c2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022ede`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022fa1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800230c2`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x180023079`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x180023079`
- `SETUPAPI!SetupCloseInfFile` at `0x1800231c7`
- `SETUPAPI!SetupCloseInfFile` at `0x180023270`
- `SETUPAPI!SetupCloseInfFile` at `0x1800231c7`
- `SETUPAPI!SetupCloseInfFile` at `0x180023270`
- `SETUPAPI!SetupInstallFromInfSectionW` at `0x1800231a8`
- `SETUPAPI!SetupInstallFromInfSectionW` at `0x1800231a8`

## string_xrefs

- `0x180022fcf`: `InstallAllInfSections failed`
- `0x1800231dd`: `Invalid Argument: hDevInfo=%p, CopyQueue=%p, pLocalData=%p`
- `0x180022e64`: `PerformInfInstallActions`
- `0x1800231e4`: `PerformInfInstallActions`
- `0x180022ff4`: `PerformInfInstallActions`
- `0x18002310c`: `PerformInfInstallActions`
- `0x18002323e`: `PerformInfInstallActions`
- `0x1800232bc`: `PerformInfInstallActions`
- `0x180022e5d`: `Parsing INF and storing files to copy`
- `0x1800230ea`: `CheckAndEnqueueMonitorDll failed (see additional info)`

## pseudocode

```c
__int64 __fastcall PerformInfInstallActions(
        HDEVINFO DeviceInfoSet,
        char *a2,
        unsigned __int16 *a3,
        __int64 a4,
        unsigned int a5,
        int a6)
{
  int v10; // eax
  LPWSTR v11; // r13
  signed int LastErrorAsFailHR; // edi
  NCoreLibrary *v13; // rcx
  DWORD LastError; // eax
  int v15; // edx
  unsigned int v16; // r9d
  const unsigned __int16 *v17; // rcx
  const unsigned __int16 *v18; // rax
  NCoreLibrary *v19; // rcx
  DWORD v20; // eax
  int v21; // edx
  const unsigned __int16 *v22; // rcx
  __int64 v23; // r14
  __int64 v24; // rax
  __int64 v25; // r14
  NCoreLibrary *v26; // rcx
  DWORD v27; // eax
  int v28; // edx
  const unsigned __int16 *v29; // rcx
  const unsigned __int16 *v30; // rax
  const unsigned __int16 *v31; // rcx
  const unsigned __int16 *v32; // rdx
  int v33; // edx
  const unsigned __int16 *v34; // rcx
  LPWSTR FilePart; // [rsp+60h] [rbp-A0h] BYREF
  HINF InfHandle; // [rsp+68h] [rbp-98h] BYREF
  __int64 v38[2]; // [rsp+70h] [rbp-90h] BYREF
  WCHAR Buffer[264]; // [rsp+80h] [rbp-80h] BYREF

  FilePart = (LPWSTR)-1LL;
  InfHandle = (HINF)-1LL;
  *(_OWORD *)v38 = 0;
  if ( DeviceInfoSet == (HDEVINFO)-1LL || a2 == (char *)-1LL || !a4 )
  {
    LastErrorAsFailHR = -2147024809;
    ClassInstallerTelemetry::WriteDbgTraceError(
      "PerformInfInstallActions",
      L"Invalid Argument: hDevInfo=%p, CopyQueue=%p, pLocalData=%p",
      DeviceInfoSet,
      a2,
      a4);
    if ( a4 )
    {
      v30 = *(const unsigned __int16 **)a4;
      v31 = *(const unsigned __int16 **)(a4 + 8);
      v32 = *(const unsigned __int16 **)(a4 + 16);
    }
    else
    {
      v30 = 0;
      v31 = 0;
      v32 = 0;
    }
    SplLogPrinterSetupEvent(
      &SETUP_PARSEINF_FAILED,
      L"PerformInfInstallActions",
      0,
      0,
      v30,
      v31,
      v32,
      (const unsigned __int16 *)PlatformEnv[a5],
      0x57u,
      0x80070057);
    goto LABEL_45;
  }
  ClassInstallerTelemetry::WriteDbgTraceInfo("PerformInfInstallActions", L"Parsing INF and storing files to copy");
  v10 = OpenPrinterInf(a4, a5, &FilePart);
  v11 = FilePart;
  LastErrorAsFailHR = v10;
  if ( v10 >= 0 )
  {
    LastErrorAsFailHR = 0;
    if ( !ParseInf(DeviceInfoSet, (_QWORD *)a4, a5, a3, 0, -1, 0, 128, (__int64 *)&InfHandle, (struct _HINF_ARRAY *)v38) )
    {
      LastErrorAsFailHR = NCoreLibrary::GetLastErrorAsFailHR(v13);
      if ( LastErrorAsFailHR < 0 )
      {
        LastError = GetLastError();
        v15 = *(_DWORD *)(a4 + 172);
        v16 = LastError;
        if ( v15 )
          v17 = *(const unsigned __int16 **)(a4 + 224);
        else
          v17 = 0;
        v18 = *(const unsigned __int16 **)(a4 + 184);
        if ( !v18 )
          v18 = *(const unsigned __int16 **)(a4 + 16);
        SplLogPrinterSetupCoreDriverEvent(
          &SETUP_INSTALL_PRINTER_DRIVER_FAILED,
          L"PerformInfInstallActions",
          L"ParseInf failed",
          0,
          *(const unsigned __int16 **)a4,
          *(const unsigned __int16 **)(a4 + 8),
          v18,
          (const unsigned __int16 *)PlatformEnv[a5],
          v15,
          v17,
          v16,
          LastErrorAsFailHR);
        goto LABEL_39;
      }
      LastErrorAsFailHR = 0;
    }
    if ( !(unsigned int)InstallAllInfSections(
                          (struct _PSETUP_LOCAL_DATA *)a4,
                          a5,
                          (__int64)a3,
                          a2,
                          0,
                          128,
                          v11,
                          *(PCWSTR *)(a4 + 184),
                          (__int64)InfHandle,
                          (unsigned int *)v38,
                          a4 + 400) )
    {
      LastErrorAsFailHR = NCoreLibrary::GetLastErrorAsFailHR(v19);
      if ( LastErrorAsFailHR < 0 )
      {
        v20 = GetLastError();
        v21 = *(_DWORD *)(a4 + 172);
        if ( v21 )
          v22 = *(const unsigned __int16 **)(a4 + 224);
        else
          v22 = 0;
        SplLogPrinterSetupCoreDriverEvent(
          &SETUP_INSTALL_PRINTER_DRIVER_FAILED,
          L"PerformInfInstallActions",
          L"InstallAllInfSections failed",
          0,
          *(const unsigned __int16 **)a4,
          *(const unsigned __int16 **)(a4 + 8),
          *(const unsigned __int16 **)(a4 + 184),
          (const unsigned __int16 *)PlatformEnv[a5],
          v21,
          v22,
          v20,
          LastErrorAsFailHR);
        goto LABEL_39;
      }
    }
    v23 = *(_QWORD *)(a4 + 328);
    if ( !v23 || a5 != MyPlatform )
    {
LABEL_34:
      if ( MyPlatform == a5 )
        CheckAndKeepPreviousNames(0);
      if ( !a6 && a5 == MyPlatform )
        SetupInstallFromInfSectionW(
          HWND_MESSAGE|0x2LL,
          v11,
          *(PCWSTR *)(a4 + 184),
          0x7EFu,
          0,
          0,
          0,
          0,
          0,
          DeviceInfoSet,
          0);
      goto LABEL_39;
    }
    memset_0(Buffer, 0, 0x208u);
    FilePart = 0;
    v24 = -1;
    do
      ++v24;
    while ( *(_WORD *)(v23 + 2 * v24) );
    v25 = v23 + 2 * v24;
    if ( GetFullPathNameW(*(LPCWSTR *)a4, 0x104u, Buffer, &FilePart) && FilePart )
      *FilePart = 0;
    if ( (unsigned int)CheckAndEnqueueMonitorDll((PCWSTR)(v25 + 2)) )
    {
      LastErrorAsFailHR = 0;
      goto LABEL_34;
    }
    LastErrorAsFailHR = NCoreLibrary::GetLastErrorAsFailHR(v26);
    if ( LastErrorAsFailHR >= 0 )
      goto LABEL_34;
    v27 = GetLastError();
    v28 = *(_DWORD *)(a4 + 172);
    if ( v28 )
      v29 = *(const unsigned __int16 **)(a4 + 224);
    else
      v29 = 0;
    SplLogPrinterSetupCoreDriverEvent(
      &SETUP_INSTALL_PRINTER_DRIVER_FAILED,
      L"PerformInfInstallActions",
      L"CheckAndEnqueueMonitorDll failed (see additional info)",
      (const unsigned __int16 *)(v25 + 2),
      *(const unsigned __int16 **)a4,
      *(const unsigned __int16 **)(a4 + 8),
      *(const unsigned __int16 **)(a4 + 184),
      (const unsigned __int16 *)PlatformEnv[a5],
      v28,
      v29,
      v27,
      LastErrorAsFailHR);
  }
LABEL_39:
  if ( v11 != (LPWSTR)-1LL )
    SetupCloseInfFile(v11);
LABEL_45:
  FreeInfArray(v38);
  if ( InfHandle != (HINF)-1LL )
  {
    SetupCloseInfFile(InfHandle);
    InfHandle = (HINF)-1LL;
  }
  if ( LastErrorAsFailHR >= 0 )
  {
    v33 = *(_DWORD *)(a4 + 172);
    if ( v33 )
      v34 = *(const unsigned __int16 **)(a4 + 224);
    else
      v34 = 0;
    SplLogPrinterSetupCoreDriverEvent(
      &SETUP_INSTALL_PRINTER_DRIVER_SUCCEEDED,
      L"PerformInfInstallActions",
      0,
      0,
      *(const unsigned __int16 **)a4,
      *(const unsigned __int16 **)(a4 + 8),
      *(const unsigned __int16 **)(a4 + 184),
      (const unsigned __int16 *)PlatformEnv[a5],
      v33,
      v34,
      0,
      LastErrorAsFailHR);
  }
  return (unsigned int)LastErrorAsFailHR;
}

```

## disassembly

```asm
0x180022dec  push    rbp
0x180022dee  push    rbx
0x180022def  push    rsi
0x180022df0  push    rdi
0x180022df1  push    r12
0x180022df3  push    r13
0x180022df5  push    r14
0x180022df7  push    r15
0x180022df9  lea     rbp, [rsp-1A8h]
0x180022e01  sub     rsp, 2A8h
0x180022e08  mov     rax, cs:__security_cookie
0x180022e0f  xor     rax, rsp
0x180022e12  mov     [rbp+1E0h+var_50], rax
0x180022e19  movsxd  rsi, [rbp+1E0h+arg_20]
0x180022e20  or      rax, 0FFFFFFFFFFFFFFFFh
0x180022e24  mov     [rsp+2E0h+FilePart], rax
0x180022e29  xorps   xmm0, xmm0
0x180022e2c  mov     [rsp+2E0h+InfHandle], rax
0x180022e31  mov     rbx, r9
0x180022e34  mov     r14, r8
0x180022e37  mov     r15, rdx
0x180022e3a  mov     r12, rcx
0x180022e3d  movups  xmmword ptr [rsp+2E0h+var_270], xmm0
0x180022e42  cmp     rcx, rax
0x180022e45  jz      loc_1800231D2
0x180022e4b  cmp     rdx, rax
0x180022e4e  jz      loc_1800231D2
0x180022e54  test    rbx, rbx
0x180022e57  jz      loc_1800231D2
0x180022e5d  lea     rdx, aParsingInfAndS; "Parsing INF and storing files to copy"
0x180022e64  lea     rcx, aPerforminfinst_1; "PerformInfInstallActions"
0x180022e6b  call    ?WriteDbgTraceInfo@ClassInstallerTelemetry@@SAXPEADPEAGZZ; ClassInstallerTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x180022e70  lea     r8, [rsp+2E0h+FilePart]
0x180022e75  mov     edx, esi
0x180022e77  mov     rcx, rbx
0x180022e7a  call    ?OpenPrinterInf@@YAJPEAU_PSETUP_LOCAL_DATA@@W4PLATFORM@@PEAPEAX@Z; OpenPrinterInf(_PSETUP_LOCAL_DATA *,PLATFORM,void * *)
0x180022e7f  mov     r13, [rsp+2E0h+FilePart]
0x180022e84  mov     edi, eax
0x180022e86  test    eax, eax
0x180022e88  js      loc_1800231B0
0x180022e8e  lea     rax, [rsp+2E0h+var_270]
0x180022e93  xor     edi, edi
0x180022e95  mov     [rsp+2E0h+DeviceInfoSet], rax
0x180022e9a  mov     r9, r14
0x180022e9d  lea     rax, [rsp+2E0h+InfHandle]
0x180022ea2  mov     r8d, esi
0x180022ea5  mov     [rsp+2E0h+Context], rax
0x180022eaa  mov     rdx, rbx
0x180022ead  mov     dword ptr [rsp+2E0h+MsgHandler], 80h
0x180022eb5  mov     rcx, r12
0x180022eb8  mov     qword ptr [rsp+2E0h+CopyFlags], rdi
0x180022ebd  mov     [rsp+2E0h+SourceRootPath], 0FFFFFFFFFFFFFFFFh
0x180022ec6  mov     dword ptr [rsp+2E0h+RelativeKeyRoot], edi
0x180022eca  call    ParseInf
0x180022ecf  test    eax, eax
0x180022ed1  jnz     short loc_180022F40
0x180022ed3  call    ?GetLastErrorAsFailHR@NCoreLibrary@@YAJXZ; NCoreLibrary::GetLastErrorAsFailHR(void)
0x180022ed8  mov     edi, eax
0x180022eda  test    eax, eax
0x180022edc  jns     short loc_180022F3E
0x180022ede  call    cs:__imp_GetLastError
0x180022ee4  mov     edx, [rbx+0ACh]
0x180022eea  xor     r15d, r15d
0x180022eed  mov     r9d, eax
0x180022ef0  test    edx, edx
0x180022ef2  jz      short loc_180022EFD
0x180022ef4  mov     rcx, [rbx+0E0h]
0x180022efb  jmp     short loc_180022F00
0x180022efd  mov     rcx, r15
0x180022f00  mov     rax, [rbx+0B8h]
0x180022f07  lea     r14, PlatformEnv
0x180022f0e  mov     r8, [r14+rsi*8]
0x180022f12  test    rax, rax
0x180022f15  jnz     short loc_180022F1B
0x180022f17  mov     rax, [rbx+10h]
0x180022f1b  mov     [rsp+2E0h+var_288], edi
0x180022f1f  mov     dword ptr [rsp+2E0h+DeviceInfoData], r9d
0x180022f24  mov     [rsp+2E0h+DeviceInfoSet], rcx
0x180022f29  mov     dword ptr [rsp+2E0h+Context], edx
0x180022f2d  mov     [rsp+2E0h+MsgHandler], r8
0x180022f32  lea     r8, aParseinfFailed; "ParseInf failed"
0x180022f39  jmp     loc_180022FEF
0x180022f3e  xor     edi, edi
0x180022f40  lea     rax, [rbx+190h]
0x180022f47  mov     r9, r15
0x180022f4a  mov     [rsp+2E0h+DeviceInfoData], rax; __int64
0x180022f4f  mov     r8, r14
0x180022f52  lea     rax, [rsp+2E0h+var_270]
0x180022f57  mov     edx, esi
0x180022f59  mov     [rsp+2E0h+DeviceInfoSet], rax; __int64
0x180022f5e  mov     rcx, rbx; struct _PSETUP_LOCAL_DATA *
0x180022f61  mov     rax, [rsp+2E0h+InfHandle]
0x180022f66  mov     [rsp+2E0h+Context], rax; __int64
0x180022f6b  mov     rax, [rbx+0B8h]
0x180022f72  mov     [rsp+2E0h+MsgHandler], rax; SectionName
0x180022f77  mov     qword ptr [rsp+2E0h+CopyFlags], r13; InfHandle
0x180022f7c  mov     dword ptr [rsp+2E0h+SourceRootPath], 80h; char
0x180022f84  mov     [rsp+2E0h+RelativeKeyRoot], rdi; PCWSTR
0x180022f89  call    InstallAllInfSections
0x180022f8e  test    eax, eax
0x180022f90  jnz     loc_180023020
0x180022f96  call    ?GetLastErrorAsFailHR@NCoreLibrary@@YAJXZ; NCoreLibrary::GetLastErrorAsFailHR(void)
0x180022f9b  mov     edi, eax
0x180022f9d  test    eax, eax
0x180022f9f  jns     short loc_180023020
0x180022fa1  call    cs:__imp_GetLastError
0x180022fa7  mov     edx, [rbx+0ACh]
0x180022fad  xor     r15d, r15d
0x180022fb0  test    edx, edx
0x180022fb2  jz      short loc_180022FBD
0x180022fb4  mov     rcx, [rbx+0E0h]
0x180022fbb  jmp     short loc_180022FC0
0x180022fbd  mov     rcx, r15
0x180022fc0  mov     [rsp+2E0h+var_288], edi; unsigned int
0x180022fc4  lea     r14, PlatformEnv
0x180022fcb  mov     dword ptr [rsp+2E0h+DeviceInfoData], eax; unsigned int
0x180022fcf  lea     r8, aInstallallinfs_1; "InstallAllInfSections failed"
0x180022fd6  mov     rax, [r14+rsi*8]
0x180022fda  mov     [rsp+2E0h+DeviceInfoSet], rcx; unsigned __int16 *
0x180022fdf  mov     dword ptr [rsp+2E0h+Context], edx; int
0x180022fe3  mov     [rsp+2E0h+MsgHandler], rax; unsigned __int16 *
0x180022fe8  mov     rax, [rbx+0B8h]
0x180022fef  mov     qword ptr [rsp+2E0h+CopyFlags], rax; unsigned __int16 *
0x180022ff4  lea     rdx, aPerforminfinst_0; "PerformInfInstallActions"
0x180022ffb  mov     rax, [rbx+8]
0x180022fff  lea     rcx, SETUP_INSTALL_PRINTER_DRIVER_FAILED; struct _EVENT_DESCRIPTOR *
0x180023006  mov     [rsp+2E0h+SourceRootPath], rax; unsigned __int16 *
0x18002300b  xor     r9d, r9d; unsigned __int16 *
0x18002300e  mov     rax, [rbx]
0x180023011  mov     [rsp+2E0h+RelativeKeyRoot], rax; unsigned __int16 *
0x180023016  call    ?SplLogPrinterSetupCoreDriverEvent@@YAXPEBU_EVENT_DESCRIPTOR@@PEBG111111H1KK@Z; SplLogPrinterSetupCoreDriverEvent(_EVENT_DESCRIPTOR const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,int,ushort const *,ulong,ulong)
0x18002301b  jmp     loc_1800231BA
0x180023020  mov     r14, [rbx+148h]
0x180023027  test    r14, r14
0x18002302a  jz      loc_18002313C
0x180023030  cmp     esi, cs:MyPlatform
0x180023036  jnz     loc_18002313C
0x18002303c  xor     edx, edx; Val
0x18002303e  lea     rcx, [rbp+1E0h+Buffer]; void *
0x180023042  mov     r8d, 208h; Size
0x180023048  call    memset_0
0x18002304d  xor     ecx, ecx
0x18002304f  mov     [rsp+2E0h+FilePart], rcx
0x180023054  mov     edi, ecx
0x180023056  or      rax, 0FFFFFFFFFFFFFFFFh
0x18002305a  inc     rax
0x18002305d  cmp     [r14+rax*2], cx
0x180023062  jnz     short loc_18002305A
0x180023064  mov     rcx, [rbx]; lpFileName
0x180023067  lea     r9, [rsp+2E0h+FilePart]; lpFilePart
0x18002306c  lea     r8, [rbp+1E0h+Buffer]; lpBuffer
0x180023070  mov     edx, 104h; nBufferLength
0x180023075  lea     r14, [r14+rax*2]
0x180023079  call    cs:__imp_GetFullPathNameW
0x18002307f  xor     edx, edx
0x180023081  test    eax, eax
0x180023083  jz      short loc_180023096
0x180023085  mov     rcx, [rsp+2E0h+FilePart]
0x18002308a  test    rcx, rcx
0x18002308d  jz      short loc_180023096
0x18002308f  mov     [rcx], dx
0x180023092  lea     rdi, [rbp+1E0h+Buffer]
0x180023096  mov     r9, r13
0x180023099  lea     rcx, [r14+2]; FileName
0x18002309d  mov     r8, r15
0x1800230a0  mov     rdx, rdi
0x1800230a3  call    CheckAndEnqueueMonitorDll
0x1800230a8  xor     r15d, r15d
0x1800230ab  test    eax, eax
0x1800230ad  jz      short loc_1800230B7
0x1800230af  mov     edi, r15d
0x1800230b2  jmp     loc_18002313F
0x1800230b7  call    ?GetLastErrorAsFailHR@NCoreLibrary@@YAJXZ; NCoreLibrary::GetLastErrorAsFailHR(void)
0x1800230bc  mov     edi, eax
0x1800230be  test    eax, eax
0x1800230c0  jns     short loc_18002313F
0x1800230c2  call    cs:__imp_GetLastError
0x1800230c8  mov     edx, [rbx+0ACh]
0x1800230ce  test    edx, edx
0x1800230d0  jz      short loc_1800230DB
0x1800230d2  mov     rcx, [rbx+0E0h]
0x1800230d9  jmp     short loc_1800230DE
0x1800230db  mov     rcx, r15
0x1800230de  mov     [rsp+2E0h+var_288], edi; unsigned int
0x1800230e2  lea     r9, [r14+2]; unsigned __int16 *
0x1800230e6  mov     dword ptr [rsp+2E0h+DeviceInfoData], eax; unsigned int
0x1800230ea  lea     r8, aCheckandenqueu; "CheckAndEnqueueMonitorDll failed (see a"...
0x1800230f1  mov     [rsp+2E0h+DeviceInfoSet], rcx; unsigned __int16 *
0x1800230f6  lea     rcx, PlatformEnv
0x1800230fd  mov     rax, [rcx+rsi*8]
0x180023101  lea     rcx, SETUP_INSTALL_PRINTER_DRIVER_FAILED; struct _EVENT_DESCRIPTOR *
0x180023108  mov     dword ptr [rsp+2E0h+Context], edx; int
0x18002310c  lea     rdx, aPerforminfinst_0; "PerformInfInstallActions"
0x180023113  mov     [rsp+2E0h+MsgHandler], rax; unsigned __int16 *
0x180023118  mov     rax, [rbx+0B8h]
0x18002311f  mov     qword ptr [rsp+2E0h+CopyFlags], rax; unsigned __int16 *
0x180023124  mov     rax, [rbx+8]
0x180023128  mov     [rsp+2E0h+SourceRootPath], rax; unsigned __int16 *
0x18002312d  mov     rax, [rbx]
0x180023130  mov     [rsp+2E0h+RelativeKeyRoot], rax; unsigned __int16 *
0x180023135  call    ?SplLogPrinterSetupCoreDriverEvent@@YAXPEBU_EVENT_DESCRIPTOR@@PEBG111111H1KK@Z; SplLogPrinterSetupCoreDriverEvent(_EVENT_DESCRIPTOR const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,int,ushort const *,ulong,ulong)
0x18002313a  jmp     short loc_1800231B3
0x18002313c  xor     r15d, r15d
0x18002313f  cmp     cs:MyPlatform, esi
0x180023145  jnz     short loc_18002315C
0x180023147  lea     r8, [rbx+58h]
0x18002314b  mov     r9d, esi
0x18002314e  lea     rdx, [rbx+108h]
0x180023155  xor     ecx, ecx; pName
0x180023157  call    CheckAndKeepPreviousNames
0x18002315c  test    edi, edi
0x18002315e  js      short loc_1800231B3
0x180023160  cmp     [rbp+1E0h+arg_28], r15d
0x180023167  jnz     short loc_1800231B3
0x180023169  cmp     esi, cs:MyPlatform
0x18002316f  jnz     short loc_1800231B3
0x180023171  mov     r8, [rbx+0B8h]; SectionName
0x180023178  mov     r9d, 7EFh; Flags
0x18002317e  mov     [rsp+2E0h+DeviceInfoData], r15; DeviceInfoData
0x180023183  mov     rdx, r13; InfHandle
0x180023186  mov     [rsp+2E0h+DeviceInfoSet], r12; DeviceInfoSet
0x18002318b  or      rcx, 0FFFFFFFFFFFFFFFFh; Owner
0x18002318f  mov     [rsp+2E0h+Context], r15; Context
0x180023194  mov     [rsp+2E0h+MsgHandler], r15; MsgHandler
0x180023199  mov     [rsp+2E0h+CopyFlags], r15d; CopyFlags
0x18002319e  mov     [rsp+2E0h+SourceRootPath], r15; SourceRootPath
0x1800231a3  mov     [rsp+2E0h+RelativeKeyRoot], r15; RelativeKeyRoot
0x1800231a8  call    cs:__imp_SetupInstallFromInfSectionW
0x1800231ae  jmp     short loc_1800231B3
0x1800231b0  xor     r15d, r15d
0x1800231b3  lea     r14, PlatformEnv
0x1800231ba  cmp     r13, 0FFFFFFFFFFFFFFFFh
0x1800231be  jz      loc_18002325B
0x1800231c4  mov     rcx, r13; InfHandle
0x1800231c7  call    cs:__imp_SetupCloseInfFile
0x1800231cd  jmp     loc_18002325B
0x1800231d2  mov     r9, r15
0x1800231d5  mov     [rsp+2E0h+RelativeKeyRoot], rbx
0x1800231da  mov     r8, r12
0x1800231dd  lea     rdx, aInvalidArgumen_11; "Invalid Argument: hDevInfo=%p, CopyQueu"...
0x1800231e4  lea     rcx, aPerforminfinst_1; "PerformInfInstallActions"
0x1800231eb  mov     edi, 80070057h
0x1800231f0  call    ?WriteDbgTraceError@ClassInstallerTelemetry@@SAXPEADPEAGZZ; ClassInstallerTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x1800231f5  xor     r15d, r15d
0x1800231f8  lea     r14, PlatformEnv
0x1800231ff  mov     r8, [r14+rsi*8]
0x180023203  test    rbx, rbx
0x180023206  jz      short loc_180023215
0x180023208  mov     rax, [rbx]
0x18002320b  mov     rcx, [rbx+8]
0x18002320f  mov     rdx, [rbx+10h]
0x180023213  jmp     short loc_18002321E
0x180023215  mov     rax, r15
0x180023218  mov     rcx, r15
0x18002321b  mov     rdx, r15
0x18002321e  mov     dword ptr [rsp+2E0h+DeviceInfoSet], 80070057h; unsigned int
0x180023226  xor     r9d, r9d; unsigned __int16 *
0x180023229  mov     dword ptr [rsp+2E0h+Context], 57h ; 'W'; unsigned int
0x180023231  mov     [rsp+2E0h+MsgHandler], r8; unsigned __int16 *
0x180023236  xor     r8d, r8d; unsigned __int16 *
0x180023239  mov     qword ptr [rsp+2E0h+CopyFlags], rdx; unsigned __int16 *
0x18002323e  lea     rdx, aPerforminfinst_0; "PerformInfInstallActions"
0x180023245  mov     [rsp+2E0h+SourceRootPath], rcx; unsigned __int16 *
0x18002324a  lea     rcx, SETUP_PARSEINF_FAILED; struct _EVENT_DESCRIPTOR *
0x180023251  mov     [rsp+2E0h+RelativeKeyRoot], rax; unsigned __int16 *
0x180023256  call    ?SplLogPrinterSetupEvent@@YAXPEBU_EVENT_DESCRIPTOR@@PEBG111111KK@Z; SplLogPrinterSetupEvent(_EVENT_DESCRIPTOR const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ulong,ulong)
0x18002325b  lea     rcx, [rsp+2E0h+var_270]
0x180023260  call    FreeInfArray
0x180023265  mov     rcx, [rsp+2E0h+InfHandle]; InfHandle
0x18002326a  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18002326e  jz      short loc_18002327F
0x180023270  call    cs:__imp_SetupCloseInfFile
0x180023276  mov     [rsp+2E0h+InfHandle], 0FFFFFFFFFFFFFFFFh
0x18002327f  test    edi, edi
0x180023281  js      short loc_1800232EA
0x180023283  mov     edx, [rbx+0ACh]
0x180023289  test    edx, edx
0x18002328b  jz      short loc_180023296
0x18002328d  mov     rcx, [rbx+0E0h]
0x180023294  jmp     short loc_180023299
0x180023296  mov     rcx, r15
0x180023299  mov     rax, [r14+rsi*8]
0x18002329d  xor     r9d, r9d; unsigned __int16 *
0x1800232a0  mov     [rsp+2E0h+var_288], edi; unsigned int
0x1800232a4  xor     r8d, r8d; unsigned __int16 *
0x1800232a7  mov     dword ptr [rsp+2E0h+DeviceInfoData], r15d; unsigned int
0x1800232ac  mov     [rsp+2E0h+DeviceInfoSet], rcx; unsigned __int16 *
0x1800232b1  lea     rcx, SETUP_INSTALL_PRINTER_DRIVER_SUCCEEDED; struct _EVENT_DESCRIPTOR *
0x1800232b8  mov     dword ptr [rsp+2E0h+Context], edx; int
0x1800232bc  lea     rdx, aPerforminfinst_0; "PerformInfInstallActions"
0x1800232c3  mov     [rsp+2E0h+MsgHandler], rax; unsigned __int16 *
0x1800232c8  mov     rax, [rbx+0B8h]
0x1800232cf  mov     qword ptr [rsp+2E0h+CopyFlags], rax; unsigned __int16 *
0x1800232d4  mov     rax, [rbx+8]
0x1800232d8  mov     [rsp+2E0h+SourceRootPath], rax; unsigned __int16 *
0x1800232dd  mov     rax, [rbx]
0x1800232e0  mov     [rsp+2E0h+RelativeKeyRoot], rax; unsigned __int16 *
0x1800232e5  call    ?SplLogPrinterSetupCoreDriverEvent@@YAXPEBU_EVENT_DESCRIPTOR@@PEBG111111H1KK@Z; SplLogPrinterSetupCoreDriverEvent(_EVENT_DESCRIPTOR const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,int,ushort const *,ulong,ulong)
0x1800232ea  mov     eax, edi
0x1800232ec  mov     rcx, [rbp+1E0h+var_50]
  ... truncated ...
```
