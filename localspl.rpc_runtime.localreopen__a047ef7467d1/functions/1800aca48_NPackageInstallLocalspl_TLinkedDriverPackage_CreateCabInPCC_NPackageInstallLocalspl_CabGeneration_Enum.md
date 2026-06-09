# NPackageInstallLocalspl::TLinkedDriverPackage::CreateCabInPCC(NPackageInstallLocalspl::CabGeneration::Enum)

- ea: `0x1800aca48`
- end: `0x1800acd34`
- name: `?CreateCabInPCC@TLinkedDriverPackage@NPackageInstallLocalspl@@QEAAJW4Enum@CabGeneration@2@@Z`
- size: `748`
- prototype: ``
- caller_count: `2`
- callee_count: `14`
- tags: `file_ops, registry_config, installer_update`

## callers

- `0x18000f270`
- `0x1800315ac`

## callees

- `0x18000c7ec`
- `0x180011f00`
- `0x180014e50`
- `0x180015e28`
- `0x180025cd8`
- `0x180032d4c`
- `0x18003e984`
- `0x18003ea2c`
- `0x180044f10`
- `0x180046a20`
- `0x180046a5c`
- `0x1800aca48`
- `0x1800b8b94`
- `0x1800cfa54`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x1800acbfd`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x1800acbfd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800acb37`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800acb37`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x1800acc83`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x1800acc83`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800acc91`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800acc91`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x1800acb2d`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x1800acb2d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800acadd`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800acadd`

## string_xrefs

- `0x1800aca7a`: `Entering CreateCabInPCC (path='%ws', cabGeneration=%u)`
- `0x1800aca62`: `NPackageInstallLocalspl::TLinkedDriverPackage::CreateCabInPCC`
- `0x1800acaeb`: `Failed to write Driver Package Data to registry`
- `0x1800acb5d`: `Error creating PCC path %ws: hr: 0x%x`
- `0x1800acbb7`: `Error in RemovePreviousCab (m_strDriverStorePath='%ws'): hr: 0x%x`
- `0x1800acbe1`: `Installing %ws into the PCC`
- `0x1800accac`: `Installing %ws into the PCC`
- `0x1800acaf5`: `TLinkedDriverPackage::CreateCabInPCC`
- `0x1800accd4`: `%ws is already in the PCC.`
- `0x1800acceb`: `Error in CreateCabInPCC (path='%ws', cabGeneration=%u): hr: 0x%x`
- `0x1800acd07`: `CreateCabInPCC successful (path='%ws', cabGeneration=%u)`

## pseudocode

```c
__int64 __fastcall NPackageInstallLocalspl::TLinkedDriverPackage::CreateCabInPCC(__int64 a1, unsigned int a2)
{
  __int64 v2; // r8
  const unsigned __int16 *v5; // r14
  const unsigned __int16 *v6; // rbx
  int SubKeyUnderPackageInstallation; // eax
  HKEY v8; // rsi
  signed int LastErrorAsFailHRNoBreak; // ebx
  __int64 v10; // rax
  const wchar_t *v11; // r8
  NCoreLibrary *v12; // rcx
  int v13; // eax
  int v14; // eax
  wchar_t *v15; // r14
  unsigned __int16 *v16; // rax
  const unsigned __int16 *v17; // r8
  unsigned __int16 *v18; // rsi
  unsigned int v19; // r10d
  HANDLE Thread; // rax
  const unsigned __int16 *v21; // r8
  DWORD dwCreationFlags[2]; // [rsp+20h] [rbp-48h]
  void **lpThreadId; // [rsp+28h] [rbp-40h]
  HKEY hKey; // [rsp+70h] [rbp+8h] BYREF

  v2 = *(_QWORD *)(a1 + 64);
  hKey = 0;
  v5 = *(const unsigned __int16 **)(v2 + 48);
  v6 = *(const unsigned __int16 **)(*(_QWORD *)(v2 + 192) + 72LL);
  LocalSpoolerTelemetry::WriteDbgTraceInfo(
    "NPackageInstallLocalspl::TLinkedDriverPackage::CreateCabInPCC",
    L"Entering CreateCabInPCC (path='%ws', cabGeneration=%u)",
    *(_QWORD *)(a1 + 48),
    a2);
  SubKeyUnderPackageInstallation = NPackageInstallLocalspl::GetSubKeyUnderPackageInstallation(
                                     (NPackageInstallLocalspl *)1,
                                     (int)v5,
                                     L"DriverPackages",
                                     v6,
                                     (struct _INISPOOLER *)&hKey,
                                     lpThreadId);
  v8 = hKey;
  LastErrorAsFailHRNoBreak = SubKeyUnderPackageInstallation;
  if ( SubKeyUnderPackageInstallation >= 0 )
    LastErrorAsFailHRNoBreak = NPackageInstallLocalspl::TLinkedDriverPackage::WriteToRegistry(
                                 (NPackageInstallLocalspl::TLinkedDriverPackage *)a1,
                                 hKey);
  if ( v8 )
    RegCloseKey(v8);
  if ( LastErrorAsFailHRNoBreak >= 0 )
  {
    if ( a2 != 2 )
    {
      if ( (CreateDirectoryW(*(LPCWSTR *)(*(_QWORD *)(a1 + 64) + 64LL), 0)
         || GetLastError() == 183
         || ((v10 = *(_QWORD *)(a1 + 64)) == 0
           ? (v11 = L"(m_pEnvironment is NULL)")
           : (v11 = *(const wchar_t **)(v10 + 64)),
             LocalSpoolerTelemetry::WriteDbgTraceError(
               "NPackageInstallLocalspl::TLinkedDriverPackage::CreateCabInPCC",
               L"Error creating PCC path %ws: hr: 0x%x",
               v11,
               (unsigned int)LastErrorAsFailHRNoBreak),
             LastErrorAsFailHRNoBreak = NCoreLibrary::GetLastErrorAsFailHRNoBreak(v12),
             LastErrorAsFailHRNoBreak >= 0))
        && !(unsigned int)NPackageInstallLocalspl::TLinkedDriverPackage::IsCabInPCC((NPackageInstallLocalspl::TLinkedDriverPackage *)a1) )
      {
        LODWORD(hKey) = 0;
        v13 = NPackageInstallLocalspl::TLinkedDriverPackage::CheckInboxInf(
                (NPackageInstallLocalspl::TLinkedDriverPackage *)a1,
                (int *)&hKey);
        if ( v13 < 0 )
        {
          LocalSpoolerTelemetry::WriteDbgTraceError(
            "NPackageInstallLocalspl::TLinkedDriverPackage::CreateCabInPCC",
            L"Error in CheckInboxInf: hr: 0x%x",
            (unsigned int)v13);
        }
        else if ( (_DWORD)hKey )
        {
          v14 = NPackageInstallLocalspl::TLinkedDriverPackage::RemovePreviousCab((NPackageInstallLocalspl::TLinkedDriverPackage *)a1);
          if ( v14 < 0 )
            LocalSpoolerTelemetry::WriteDbgTraceError(
              "NPackageInstallLocalspl::TLinkedDriverPackage::CreateCabInPCC",
              L"Error in RemovePreviousCab (m_strDriverStorePath='%ws'): hr: 0x%x",
              *(_QWORD *)(a1 + 48),
              (unsigned int)v14);
        }
        LocalSpoolerTelemetry::WriteDbgTraceInfo(
          "NPackageInstallLocalspl::TLinkedDriverPackage::CreateCabInPCC",
          L"Installing %ws into the PCC",
          *(_QWORD *)(a1 + 48));
        v15 = wcsrchr(*(const wchar_t **)(a1 + 48), 0x5Cu);
        if ( !v15 )
        {
          LastErrorAsFailHRNoBreak = -2147024809;
          goto LABEL_32;
        }
        *v15 = 0;
        if ( a2 == 1 )
        {
          LastErrorAsFailHRNoBreak = 0;
          v16 = (unsigned __int16 *)operator new(0x410u);
          v17 = *(const unsigned __int16 **)(a1 + 56);
          LODWORD(hKey) = 0;
          v18 = v16;
          if ( (int)StringCchCopyW(v16, 0x104u, v17) >= 0
            && (int)StringCchCopyW(v18 + 260, v19, *(const unsigned __int16 **)(a1 + 48)) >= 0
            && (Thread = CreateThread(
                           0,
                           0,
                           NPackageInstallLocalspl::TLinkedDriverPackage::CreateCabAsync,
                           v18,
                           0,
                           (LPDWORD)&hKey)) != 0 )
          {
            CloseHandle(Thread);
          }
          else
          {
            operator delete(v18, 0x410u);
          }
        }
        else
        {
          LocalSpoolerTelemetry::WriteDbgTraceInfo(
            "NPackageInstallLocalspl::TLinkedDriverPackage::CreateCabInPCC",
            L"Installing %ws into the PCC",
            *(_QWORD *)(a1 + 48));
          LastErrorAsFailHRNoBreak = NCabbingLibrary::LegacyCabPack(
                                       *(NCabbingLibrary **)(a1 + 56),
                                       *(const unsigned __int16 **)(a1 + 48),
                                       v21);
        }
        *v15 = 92;
      }
      else
      {
        LocalSpoolerTelemetry::WriteDbgTraceInfo(
          "NPackageInstallLocalspl::TLinkedDriverPackage::CreateCabInPCC",
          L"%ws is already in the PCC.",
          *(_QWORD *)(a1 + 48));
      }
      if ( LastErrorAsFailHRNoBreak < 0 )
        goto LABEL_32;
    }
    LocalSpoolerTelemetry::WriteDbgTraceInfo(
      "NPackageInstallLocalspl::TLinkedDriverPackage::CreateCabInPCC",
      L"CreateCabInPCC successful (path='%ws', cabGeneration=%u)",
      *(_QWORD *)(a1 + 48),
      a2);
    return (unsigned int)LastErrorAsFailHRNoBreak;
  }
  SplLogPrinterSetupGenericEvent(
    &SETUP_PRINTER_OPERATION_FAILED,
    L"TLinkedDriverPackage::CreateCabInPCC",
    L"Failed to write Driver Package Data to registry",
    *(const unsigned __int16 **)(a1 + 56),
    v5,
    (unsigned __int16)LastErrorAsFailHRNoBreak,
    LastErrorAsFailHRNoBreak);
LABEL_32:
  dwCreationFlags[0] = LastErrorAsFailHRNoBreak;
  LocalSpoolerTelemetry::WriteDbgTraceError(
    "NPackageInstallLocalspl::TLinkedDriverPackage::CreateCabInPCC",
    L"Error in CreateCabInPCC (path='%ws', cabGeneration=%u): hr: 0x%x",
    *(_QWORD *)(a1 + 48),
    a2,
    *(_QWORD *)dwCreationFlags);
  return (unsigned int)LastErrorAsFailHRNoBreak;
}

```

## disassembly

```asm
0x1800aca48  mov     [rsp+arg_8], rbx
0x1800aca4d  mov     [rsp+arg_10], rbp
0x1800aca52  push    rsi
0x1800aca53  push    rdi
0x1800aca54  push    r12
0x1800aca56  push    r13
0x1800aca58  push    r14
0x1800aca5a  sub     rsp, 40h
0x1800aca5e  mov     r8, [rcx+40h]
0x1800aca62  lea     r12, aNpackageinstal_9; "NPackageInstallLocalspl::TLinkedDriverP"...
0x1800aca69  mov     ebp, edx
0x1800aca6b  mov     [rsp+68h+hKey], 0
0x1800aca74  mov     rdi, rcx
0x1800aca77  mov     r9d, edx
0x1800aca7a  lea     rdx, aEnteringCreate; "Entering CreateCabInPCC (path='%ws', ca"...
0x1800aca81  mov     rax, [r8+0C0h]
0x1800aca88  mov     r14, [r8+30h]
0x1800aca8c  mov     r8, [rcx+30h]
0x1800aca90  mov     rcx, r12; char *
0x1800aca93  mov     rbx, [rax+48h]
0x1800aca97  call    ?WriteDbgTraceInfo@LocalSpoolerTelemetry@@SAXPEADPEAGZZ; LocalSpoolerTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x1800aca9c  lea     rax, [rsp+68h+hKey]
0x1800acaa1  mov     r9, rbx; unsigned __int16 *
0x1800acaa4  lea     r8, aDriverpackages; "DriverPackages"
0x1800acaab  mov     qword ptr [rsp+68h+dwCreationFlags], rax; struct _INISPOOLER *
0x1800acab0  mov     rdx, r14; int
0x1800acab3  mov     ecx, 1; this
0x1800acab8  call    ?GetSubKeyUnderPackageInstallation@NPackageInstallLocalspl@@YAJHPEBG0PEAU_INISPOOLER@@PEAPEAX@Z; NPackageInstallLocalspl::GetSubKeyUnderPackageInstallation(int,ushort const *,ushort const *,_INISPOOLER *,void * *)
0x1800acabd  mov     rsi, [rsp+68h+hKey]
0x1800acac2  mov     ebx, eax
0x1800acac4  test    eax, eax
0x1800acac6  js      short loc_1800ACAD5
0x1800acac8  mov     rdx, rsi; void *
0x1800acacb  mov     rcx, rdi; this
0x1800acace  call    ?WriteToRegistry@TLinkedDriverPackage@NPackageInstallLocalspl@@QEAAJPEAX@Z; NPackageInstallLocalspl::TLinkedDriverPackage::WriteToRegistry(void *)
0x1800acad3  mov     ebx, eax
0x1800acad5  test    rsi, rsi
0x1800acad8  jz      short loc_1800ACAE3
0x1800acada  mov     rcx, rsi; hKey
0x1800acadd  call    cs:__imp_RegCloseKey
0x1800acae3  test    ebx, ebx
0x1800acae5  jns     short loc_1800ACB1A
0x1800acae7  mov     r9, [rdi+38h]; unsigned __int16 *
0x1800acaeb  lea     r8, aFailedToWriteD; "Failed to write Driver Package Data to "...
0x1800acaf2  movzx   eax, bx
0x1800acaf5  lea     rdx, aTlinkeddriverp; "TLinkedDriverPackage::CreateCabInPCC"
0x1800acafc  mov     [rsp+68h+var_38], ebx; unsigned int
0x1800acb00  lea     rcx, SETUP_PRINTER_OPERATION_FAILED; struct _EVENT_DESCRIPTOR *
0x1800acb07  mov     dword ptr [rsp+68h+lpThreadId], eax; unsigned int
0x1800acb0b  mov     qword ptr [rsp+68h+dwCreationFlags], r14; unsigned __int16 *
0x1800acb10  call    ?SplLogPrinterSetupGenericEvent@@YAXPEBU_EVENT_DESCRIPTOR@@PEBG111KK@Z; SplLogPrinterSetupGenericEvent(_EVENT_DESCRIPTOR const *,ushort const *,ushort const *,ushort const *,ushort const *,ulong,ulong)
0x1800acb15  jmp     loc_1800ACCE7
0x1800acb1a  cmp     ebp, 2
0x1800acb1d  jz      loc_1800ACD03
0x1800acb23  mov     rcx, [rdi+40h]
0x1800acb27  xor     edx, edx; lpSecurityAttributes
0x1800acb29  mov     rcx, [rcx+40h]; lpPathName
0x1800acb2d  call    cs:__imp_CreateDirectoryW
0x1800acb33  test    eax, eax
0x1800acb35  jnz     short loc_1800ACB7B
0x1800acb37  call    cs:__imp_GetLastError
0x1800acb3d  cmp     eax, 0B7h
0x1800acb42  jz      short loc_1800ACB7B
0x1800acb44  mov     rax, [rdi+40h]
0x1800acb48  test    rax, rax
0x1800acb4b  jz      short loc_1800ACB53
0x1800acb4d  mov     r8, [rax+40h]
0x1800acb51  jmp     short loc_1800ACB5A
0x1800acb53  lea     r8, aMPenvironmentI; "(m_pEnvironment is NULL)"
0x1800acb5a  mov     r9d, ebx
0x1800acb5d  lea     rdx, aErrorCreatingP; "Error creating PCC path %ws: hr: 0x%x"
0x1800acb64  mov     rcx, r12; char *
0x1800acb67  call    ?WriteDbgTraceError@LocalSpoolerTelemetry@@SAXPEADPEAGZZ; LocalSpoolerTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x1800acb6c  call    ?GetLastErrorAsFailHRNoBreak@NCoreLibrary@@YAJXZ; NCoreLibrary::GetLastErrorAsFailHRNoBreak(void)
0x1800acb71  mov     ebx, eax
0x1800acb73  test    eax, eax
0x1800acb75  js      loc_1800ACCD0
0x1800acb7b  mov     rcx, rdi; this
0x1800acb7e  call    ?IsCabInPCC@TLinkedDriverPackage@NPackageInstallLocalspl@@QEAAHXZ; NPackageInstallLocalspl::TLinkedDriverPackage::IsCabInPCC(void)
0x1800acb83  test    eax, eax
0x1800acb85  jnz     loc_1800ACCD0
0x1800acb8b  lea     rdx, [rsp+68h+hKey]; int *
0x1800acb90  mov     dword ptr [rsp+68h+hKey], eax
0x1800acb94  mov     rcx, rdi; this
0x1800acb97  call    ?CheckInboxInf@TLinkedDriverPackage@NPackageInstallLocalspl@@QEAAJPEAH@Z; NPackageInstallLocalspl::TLinkedDriverPackage::CheckInboxInf(int *)
0x1800acb9c  test    eax, eax
0x1800acb9e  js      short loc_1800ACBCB
0x1800acba0  cmp     dword ptr [rsp+68h+hKey], 0
0x1800acba5  jz      short loc_1800ACBDD
0x1800acba7  mov     rcx, rdi; this
0x1800acbaa  call    ?RemovePreviousCab@TLinkedDriverPackage@NPackageInstallLocalspl@@QEAAJXZ; NPackageInstallLocalspl::TLinkedDriverPackage::RemovePreviousCab(void)
0x1800acbaf  test    eax, eax
0x1800acbb1  jns     short loc_1800ACBDD
0x1800acbb3  mov     r8, [rdi+30h]
0x1800acbb7  lea     rdx, aErrorInRemovep; "Error in RemovePreviousCab (m_strDriver"...
0x1800acbbe  mov     r9d, eax
0x1800acbc1  mov     rcx, r12; char *
0x1800acbc4  call    ?WriteDbgTraceError@LocalSpoolerTelemetry@@SAXPEADPEAGZZ; LocalSpoolerTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x1800acbc9  jmp     short loc_1800ACBDD
0x1800acbcb  mov     r8d, eax
0x1800acbce  lea     rdx, aErrorInCheckin; "Error in CheckInboxInf: hr: 0x%x"
0x1800acbd5  mov     rcx, r12; char *
0x1800acbd8  call    ?WriteDbgTraceError@LocalSpoolerTelemetry@@SAXPEADPEAGZZ; LocalSpoolerTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x1800acbdd  mov     r8, [rdi+30h]
0x1800acbe1  lea     rdx, aInstallingWsIn; "Installing %ws into the PCC"
0x1800acbe8  mov     rcx, r12; char *
0x1800acbeb  call    ?WriteDbgTraceInfo@LocalSpoolerTelemetry@@SAXPEADPEAGZZ; LocalSpoolerTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x1800acbf0  mov     rcx, [rdi+30h]; Str
0x1800acbf4  mov     r13d, 5Ch ; '\'
0x1800acbfa  mov     edx, r13d; Ch
0x1800acbfd  call    cs:__imp_wcsrchr
0x1800acc03  mov     r14, rax
0x1800acc06  test    rax, rax
0x1800acc09  jnz     short loc_1800ACC15
0x1800acc0b  mov     ebx, 80070057h
0x1800acc10  jmp     loc_1800ACCE7
0x1800acc15  xor     eax, eax
0x1800acc17  mov     [r14], ax
0x1800acc1b  cmp     ebp, 1
0x1800acc1e  jnz     loc_1800ACCA8
0x1800acc24  mov     ecx, 410h; Size
0x1800acc29  xor     ebx, ebx
0x1800acc2b  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800acc30  mov     r8, [rdi+38h]; unsigned __int16 *
0x1800acc34  mov     r10d, 104h
0x1800acc3a  mov     edx, r10d; unsigned __int64
0x1800acc3d  mov     dword ptr [rsp+68h+hKey], ebx
0x1800acc41  mov     rcx, rax; unsigned __int16 *
0x1800acc44  mov     rsi, rax
0x1800acc47  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800acc4c  test    eax, eax
0x1800acc4e  js      short loc_1800ACC99
0x1800acc50  mov     r8, [rdi+30h]; unsigned __int16 *
0x1800acc54  lea     rcx, [rsi+208h]; unsigned __int16 *
0x1800acc5b  mov     edx, r10d; unsigned __int64
0x1800acc5e  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800acc63  test    eax, eax
0x1800acc65  js      short loc_1800ACC99
0x1800acc67  lea     rax, [rsp+68h+hKey]
0x1800acc6c  mov     r9, rsi; lpParameter
0x1800acc6f  mov     [rsp+68h+lpThreadId], rax; lpThreadId
0x1800acc74  lea     r8, ?CreateCabAsync@TLinkedDriverPackage@NPackageInstallLocalspl@@CAKPEAX@Z; lpStartAddress
0x1800acc7b  xor     edx, edx; dwStackSize
0x1800acc7d  mov     [rsp+68h+dwCreationFlags], ebx; dwCreationFlags
0x1800acc81  xor     ecx, ecx; lpThreadAttributes
0x1800acc83  call    cs:__imp_CreateThread
0x1800acc89  test    rax, rax
0x1800acc8c  jz      short loc_1800ACC99
0x1800acc8e  mov     rcx, rax; hObject
0x1800acc91  call    cs:__imp_CloseHandle
0x1800acc97  jmp     short loc_1800ACCCA
0x1800acc99  mov     edx, 410h; unsigned __int64
0x1800acc9e  mov     rcx, rsi; void *
0x1800acca1  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800acca6  jmp     short loc_1800ACCCA
0x1800acca8  mov     r8, [rdi+30h]
0x1800accac  lea     rdx, aInstallingWsIn; "Installing %ws into the PCC"
0x1800accb3  mov     rcx, r12; char *
0x1800accb6  call    ?WriteDbgTraceInfo@LocalSpoolerTelemetry@@SAXPEADPEAGZZ; LocalSpoolerTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x1800accbb  mov     rdx, [rdi+30h]; unsigned __int16 *
0x1800accbf  mov     rcx, [rdi+38h]; this
0x1800accc3  call    ?LegacyCabPack@NCabbingLibrary@@YAJPEBG0@Z; NCabbingLibrary::LegacyCabPack(ushort const *,ushort const *)
0x1800accc8  mov     ebx, eax
0x1800accca  mov     [r14], r13w
0x1800accce  jmp     short loc_1800ACCE3
0x1800accd0  mov     r8, [rdi+30h]
0x1800accd4  lea     rdx, aWsIsAlreadyInT; "%ws is already in the PCC."
0x1800accdb  mov     rcx, r12; char *
0x1800accde  call    ?WriteDbgTraceInfo@LocalSpoolerTelemetry@@SAXPEADPEAGZZ; LocalSpoolerTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x1800acce3  test    ebx, ebx
0x1800acce5  jns     short loc_1800ACD03
0x1800acce7  mov     r8, [rdi+30h]
0x1800acceb  lea     rdx, aErrorInCreatec; "Error in CreateCabInPCC (path='%ws', ca"...
0x1800accf2  mov     r9d, ebp
0x1800accf5  mov     [rsp+68h+dwCreationFlags], ebx
0x1800accf9  mov     rcx, r12; char *
0x1800accfc  call    ?WriteDbgTraceError@LocalSpoolerTelemetry@@SAXPEADPEAGZZ; LocalSpoolerTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x1800acd01  jmp     short loc_1800ACD19
0x1800acd03  mov     r8, [rdi+30h]
0x1800acd07  lea     rdx, aCreatecabinpcc; "CreateCabInPCC successful (path='%ws', "...
0x1800acd0e  mov     r9d, ebp
0x1800acd11  mov     rcx, r12; char *
0x1800acd14  call    ?WriteDbgTraceInfo@LocalSpoolerTelemetry@@SAXPEADPEAGZZ; LocalSpoolerTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x1800acd19  lea     r11, [rsp+68h+var_28]
0x1800acd1e  mov     eax, ebx
0x1800acd20  mov     rbx, [r11+38h]
0x1800acd24  mov     rbp, [r11+40h]
0x1800acd28  mov     rsp, r11
0x1800acd2b  pop     r14
0x1800acd2d  pop     r13
0x1800acd2f  pop     r12
0x1800acd31  pop     rdi
0x1800acd32  pop     rsi
0x1800acd33  retn
```
