# FillCatalog(ulong,ushort *)

- ea: `0x18000ac60`
- end: `0x18000af07`
- name: `?FillCatalog@@YAJKPEAG@Z`
- size: `679`
- prototype: `int(unsigned int, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `11`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x18000ca40`

## callees

- `0x180002300`
- `0x180002f48`
- `0x18000ac60`
- `0x18000af10`
- `0x18000b200`
- `0x18000d04c`
- `0x18000d57c`
- `0x18000d624`
- `0x18000ea18`
- `0x180010b48`
- `0x18003a010`

## import_xrefs

- `ntdll!RtlGetVersion` at `0x18000ad60`
- `ntdll!RtlGetVersion` at `0x18000ad60`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000ae71`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000ae71`
- `api-ms-win-core-synch-l1-1-0!CreateMutexW` at `0x18000acac`
- `api-ms-win-core-synch-l1-1-0!CreateMutexW` at `0x18000acac`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18000aeaa`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18000aeaa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ace1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ad0c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ace1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ad0c`

## string_xrefs

- `0x18000acf9`: `Couldn't create catalog mutex hr: 0x%x`
- `0x18000ae2d`: `DownloadUpdatedFiles() returned hr: 0x%x`
- `0x18000ac96`: `Global\FillWindowsUpdatePrinterCatalog`

## pseudocode

```c
__int64 __fastcall FillCatalog(__int64 a1, unsigned __int16 *a2)
{
  __int64 MutexW; // rsi
  BOOL v4; // ebx
  signed int LastError; // eax
  __int64 LastErrorAsFailHR; // rdi
  __int64 v7; // r8
  NTSTATUS Version; // edi
  NCoreLibrary *v9; // rcx
  int inited; // ebx
  unsigned int v11; // ecx
  __int64 v13; // [rsp+40h] [rbp-C0h] BYREF
  int v14; // [rsp+48h] [rbp-B8h] BYREF
  int v15; // [rsp+50h] [rbp-B0h] BYREF
  const wchar_t *v16; // [rsp+58h] [rbp-A8h]
  _OSVERSIONINFOW VersionInformation; // [rsp+70h] [rbp-90h] BYREF
  int v18; // [rsp+184h] [rbp+84h]
  _BYTE v19[16]; // [rsp+1A0h] [rbp+A0h] BYREF

  v13 = -1;
  MutexW = (__int64)CreateMutexW(0, 1, L"Global\\FillWindowsUpdatePrinterCatalog");
  NCoreLibrary::TGenericSP<void *,NCoreLibrary::TAutoHandleNT,void *,-1,void * const *>::Reset(&v13);
  if ( MutexW )
  {
    v13 = MutexW;
    if ( MutexW != -1 )
    {
      LODWORD(LastErrorAsFailHR) = 0;
      v4 = GetLastError() != 183;
      goto LABEL_8;
    }
  }
  else
  {
    MutexW = -1;
    v13 = -1;
  }
  v4 = 0;
  LastError = GetLastError();
  LODWORD(LastErrorAsFailHR) = LastError;
  if ( LastError > 0 )
    LODWORD(LastErrorAsFailHR) = (unsigned __int16)LastError | 0x80070000;
  ClassInstallerTelemetry::WriteDbgTraceError(
    "FillCatalog",
    L"Couldn't create catalog mutex hr: 0x%x",
    (unsigned int)LastErrorAsFailHR);
LABEL_8:
  if ( v4 )
  {
    v14 = 0;
    memset_0(&v15, 0, 0x148u);
    ClassInstallerTelemetry::WriteDbgTraceInfo("FillCatalog", L"Got catalog mutex");
    if ( (int)LastErrorAsFailHR >= 0 )
    {
      VersionInformation.dwOSVersionInfoSize = 276;
      Version = RtlGetVersion(&VersionInformation);
      if ( Version < 0 )
        LODWORD(LastErrorAsFailHR) = Version | 0x10000000;
      else
        LODWORD(LastErrorAsFailHR) = 0;
    }
    v9 = (NCoreLibrary *)word_180047CE4;
    v15 = 328;
    v18 = *(_DWORD *)&word_180047CE4[4 * MyPlatform];
    v16 = L"3FBF5B30-DEB4-11D1-AC97-00A0C903492B";
    if ( (Microsoft_Windows_DocumentsEnableBits & 2) != 0 )
      McGenEventWrite_EventWriteTransfer(word_180047CE4, DocPerf_Setup_FillWindowsUpdateCatalog_Start, v7, 1, v19);
    if ( (int)LastErrorAsFailHR >= 0 )
    {
      inited = InitCodedownload(0);
      LODWORD(LastErrorAsFailHR) = inited == 0 ? 0x80004005 : 0;
      ClassInstallerTelemetry::WriteDbgTraceInfo(
        "FillCatalog",
        L"InitCodedownload returned hr: 0x%x",
        (unsigned int)LastErrorAsFailHR);
      if ( inited )
      {
        if ( !(*((unsigned int (__fastcall **)(_QWORD, _QWORD, int *, unsigned __int16 *, int, int *))gpCodeDownLoadInfo
               + 3))(
                *((_QWORD *)gpCodeDownLoadInfo + 1),
                0,
                &v15,
                a2,
                260,
                &v14) )
        {
          LastErrorAsFailHR = (unsigned int)NCoreLibrary::GetLastErrorAsFailHR(v9);
          ClassInstallerTelemetry::WriteDbgTraceError(
            "FillCatalog",
            L"DownloadUpdatedFiles() returned hr: 0x%x",
            LastErrorAsFailHR);
        }
      }
    }
    if ( (Microsoft_Windows_DocumentsEnableBits & 2) != 0 )
      McGenEventWrite_EventWriteTransfer(v9, DocPerf_Setup_FillWindowsUpdateCatalog_Stop, v7, 1, v19);
    if ( MutexW == -1 )
      MutexW = 0;
    ReleaseMutex((HANDLE)MutexW);
    ClassInstallerTelemetry::WriteDbgTraceInfo("FillCatalog", L"Releasing catalog mutex");
  }
  else
  {
    if ( (int)LastErrorAsFailHR < 0 )
    {
LABEL_29:
      ClassInstallerTelemetry::WriteDbgTraceError("FillCatalog", L"Returning hr: 0x%x", (unsigned int)LastErrorAsFailHR);
      goto LABEL_30;
    }
    ClassInstallerTelemetry::WriteDbgTraceInfo("FillCatalog", L"Waiting for catalog mutex");
    if ( MutexW == -1 )
      MutexW = 0;
    WaitForSingleObject((HANDLE)MutexW, 0xFFFFFFFF);
    LODWORD(LastErrorAsFailHR) = FindPopulatedCatalogDir(v11, a2);
  }
  if ( (int)LastErrorAsFailHR < 0 )
    goto LABEL_29;
LABEL_30:
  NCoreLibrary::TGenericSP<void *,NCoreLibrary::TAutoHandleNT,void *,-1,void * const *>::Reset(&v13);
  return (unsigned int)LastErrorAsFailHR;
}

```

## disassembly

```asm
0x18000ac60  mov     [rsp-8+arg_0], rbx
0x18000ac65  mov     [rsp-8+arg_10], rsi
0x18000ac6a  push    rbp
0x18000ac6b  push    rdi
0x18000ac6c  push    r12
0x18000ac6e  push    r14
0x18000ac70  push    r15
0x18000ac72  lea     rbp, [rsp-0C0h]
0x18000ac7a  sub     rsp, 1C0h
0x18000ac81  mov     rax, cs:__security_cookie
0x18000ac88  xor     rax, rsp
0x18000ac8b  mov     [rbp+0E0h+var_30], rax
0x18000ac92  or      r12, 0FFFFFFFFFFFFFFFFh
0x18000ac96  lea     r8, Name; "Global\\FillWindowsUpdatePrinterCatalog"
0x18000ac9d  mov     r14, rdx
0x18000aca0  mov     [rsp+1E0h+var_1A0], r12
0x18000aca5  xor     ecx, ecx; lpMutexAttributes
0x18000aca7  lea     edx, [r12+2]; bInitialOwner
0x18000acac  call    cs:__imp_CreateMutexW
0x18000acb2  lea     rcx, [rsp+1E0h+var_1A0]
0x18000acb7  mov     rsi, rax
0x18000acba  call    ?Reset@?$TGenericSP@PEAXVTAutoHandleNT@NCoreLibrary@@PEAX$0?0PEBQEAX@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<void *,NCoreLibrary::TAutoHandleNT,void *,-1,void * const *>::Reset(void)
0x18000acbf  lea     r15, aFillcatalog; "FillCatalog"
0x18000acc6  test    rsi, rsi
0x18000acc9  jnz     short loc_18000ACD5
0x18000accb  mov     rsi, r12
0x18000acce  mov     [rsp+1E0h+var_1A0], r12
0x18000acd3  jmp     short loc_18000ACDF
0x18000acd5  mov     [rsp+1E0h+var_1A0], rsi
0x18000acda  cmp     rsi, r12
0x18000acdd  jnz     short loc_18000AD0A
0x18000acdf  xor     ebx, ebx
0x18000ace1  call    cs:__imp_GetLastError
0x18000ace7  mov     edi, eax
0x18000ace9  test    eax, eax
0x18000aceb  jle     short loc_18000ACF6
0x18000aced  movzx   edi, ax
0x18000acf0  or      edi, 80070000h
0x18000acf6  mov     r8d, edi
0x18000acf9  lea     rdx, aCouldnTCreateC; "Couldn't create catalog mutex hr: 0x%x"
0x18000ad00  mov     rcx, r15; char *
0x18000ad03  call    ?WriteDbgTraceError@ClassInstallerTelemetry@@SAXPEADPEAGZZ; ClassInstallerTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x18000ad08  jmp     short loc_18000AD1C
0x18000ad0a  xor     edi, edi
0x18000ad0c  call    cs:__imp_GetLastError
0x18000ad12  xor     ebx, ebx
0x18000ad14  cmp     eax, 0B7h
0x18000ad19  setnz   bl
0x18000ad1c  test    ebx, ebx
0x18000ad1e  jz      loc_18000AE88
0x18000ad24  mov     ebx, 148h
0x18000ad29  mov     [rsp+1E0h+var_198], 0
0x18000ad31  mov     r8d, ebx; Size
0x18000ad34  lea     rcx, [rsp+1E0h+var_190]; void *
0x18000ad39  xor     edx, edx; Val
0x18000ad3b  call    memset_0
0x18000ad40  lea     rdx, aGotCatalogMute; "Got catalog mutex"
0x18000ad47  mov     rcx, r15; char *
0x18000ad4a  call    ?WriteDbgTraceInfo@ClassInstallerTelemetry@@SAXPEADPEAGZZ; ClassInstallerTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x18000ad4f  test    edi, edi
0x18000ad51  js      short loc_18000AD74
0x18000ad53  lea     rcx, [rsp+1E0h+VersionInformation]; lpVersionInformation
0x18000ad58  mov     [rsp+1E0h+VersionInformation.dwOSVersionInfoSize], 114h
0x18000ad60  call    cs:__imp_RtlGetVersion
0x18000ad66  mov     edi, eax
0x18000ad68  test    eax, eax
0x18000ad6a  js      short loc_18000AD70
0x18000ad6c  xor     edi, edi
0x18000ad6e  jmp     short loc_18000AD74
0x18000ad70  bts     edi, 1Ch
0x18000ad74  test    cs:Microsoft_Windows_DocumentsEnableBits, 2
0x18000ad7b  lea     rcx, word_180047CE4
0x18000ad82  movsxd  rax, cs:MyPlatform
0x18000ad89  mov     [rsp+1E0h+var_190], ebx
0x18000ad8d  mov     eax, [rcx+rax*8]
0x18000ad90  mov     [rbp+0E0h+var_5C], eax
0x18000ad96  lea     rax, a3fbf5b30Deb411; "3FBF5B30-DEB4-11D1-AC97-00A0C903492B"
0x18000ad9d  mov     [rsp+1E0h+var_188], rax
0x18000ada2  jz      short loc_18000ADC2
0x18000ada4  lea     rax, [rbp+0E0h+var_40]
0x18000adab  mov     r9d, 1
0x18000adb1  lea     rdx, DocPerf_Setup_FillWindowsUpdateCatalog_Start
0x18000adb8  mov     [rsp+1E0h+var_1C0], rax
0x18000adbd  call    McGenEventWrite_EventWriteTransfer
0x18000adc2  test    edi, edi
0x18000adc4  js      short loc_18000AE3E
0x18000adc6  xor     ecx, ecx
0x18000adc8  call    InitCodedownload
0x18000adcd  mov     ebx, eax
0x18000adcf  lea     rdx, aInitcodedownlo_0; "InitCodedownload returned hr: 0x%x"
0x18000add6  neg     eax
0x18000add8  mov     rcx, r15; char *
0x18000addb  sbb     edi, edi
0x18000addd  not     edi
0x18000addf  and     edi, 80004005h
0x18000ade5  mov     r8d, edi
0x18000ade8  call    ?WriteDbgTraceInfo@ClassInstallerTelemetry@@SAXPEADPEAGZZ; ClassInstallerTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x18000aded  test    ebx, ebx
0x18000adef  jz      short loc_18000AE3E
0x18000adf1  mov     rcx, cs:gpCodeDownLoadInfo
0x18000adf8  lea     rdx, [rsp+1E0h+var_198]
0x18000adfd  mov     [rsp+1E0h+var_1B8], rdx
0x18000ae02  lea     r8, [rsp+1E0h+var_190]
0x18000ae07  mov     r9, r14
0x18000ae0a  mov     dword ptr [rsp+1E0h+var_1C0], 104h
0x18000ae12  xor     edx, edx
0x18000ae14  mov     rax, [rcx+18h]
0x18000ae18  mov     rcx, [rcx+8]
0x18000ae1c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ae21  test    eax, eax
0x18000ae23  jnz     short loc_18000AE3E
0x18000ae25  call    ?GetLastErrorAsFailHR@NCoreLibrary@@YAJXZ; NCoreLibrary::GetLastErrorAsFailHR(void)
0x18000ae2a  mov     r8d, eax
0x18000ae2d  lea     rdx, aDownloadupdate; "DownloadUpdatedFiles() returned hr: 0x%"...
0x18000ae34  mov     rcx, r15; char *
0x18000ae37  mov     edi, eax
0x18000ae39  call    ?WriteDbgTraceError@ClassInstallerTelemetry@@SAXPEADPEAGZZ; ClassInstallerTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x18000ae3e  test    cs:Microsoft_Windows_DocumentsEnableBits, 2
0x18000ae45  jz      short loc_18000AE65
0x18000ae47  lea     rax, [rbp+0E0h+var_40]
0x18000ae4e  mov     r9d, 1
0x18000ae54  lea     rdx, DocPerf_Setup_FillWindowsUpdateCatalog_Stop
0x18000ae5b  mov     [rsp+1E0h+var_1C0], rax
0x18000ae60  call    McGenEventWrite_EventWriteTransfer
0x18000ae65  xor     eax, eax
0x18000ae67  cmp     rsi, r12
0x18000ae6a  cmovz   rsi, rax
0x18000ae6e  mov     rcx, rsi; hMutex
0x18000ae71  call    cs:__imp_ReleaseMutex
0x18000ae77  lea     rdx, aReleasingCatal; "Releasing catalog mutex"
0x18000ae7e  mov     rcx, r15; char *
0x18000ae81  call    ?WriteDbgTraceInfo@ClassInstallerTelemetry@@SAXPEADPEAGZZ; ClassInstallerTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x18000ae86  jmp     short loc_18000AEBA
0x18000ae88  test    edi, edi
0x18000ae8a  js      short loc_18000AEBE
0x18000ae8c  lea     rdx, aWaitingForCata; "Waiting for catalog mutex"
0x18000ae93  mov     rcx, r15; char *
0x18000ae96  call    ?WriteDbgTraceInfo@ClassInstallerTelemetry@@SAXPEADPEAGZZ; ClassInstallerTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x18000ae9b  xor     eax, eax
0x18000ae9d  cmp     rsi, r12
0x18000aea0  cmovz   rsi, rax
0x18000aea4  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18000aea7  mov     rcx, rsi; hHandle
0x18000aeaa  call    cs:__imp_WaitForSingleObject
0x18000aeb0  mov     rdx, r14; unsigned __int16 *
0x18000aeb3  call    ?FindPopulatedCatalogDir@@YAJKPEAG@Z; FindPopulatedCatalogDir(ulong,ushort *)
0x18000aeb8  mov     edi, eax
0x18000aeba  test    edi, edi
0x18000aebc  jns     short loc_18000AED0
0x18000aebe  mov     r8d, edi
0x18000aec1  lea     rdx, aReturningHr0xX; "Returning hr: 0x%x"
0x18000aec8  mov     rcx, r15; char *
0x18000aecb  call    ?WriteDbgTraceError@ClassInstallerTelemetry@@SAXPEADPEAGZZ; ClassInstallerTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x18000aed0  lea     rcx, [rsp+1E0h+var_1A0]
0x18000aed5  call    ?Reset@?$TGenericSP@PEAXVTAutoHandleNT@NCoreLibrary@@PEAX$0?0PEBQEAX@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<void *,NCoreLibrary::TAutoHandleNT,void *,-1,void * const *>::Reset(void)
0x18000aeda  mov     eax, edi
0x18000aedc  mov     rcx, [rbp+0E0h+var_30]
0x18000aee3  xor     rcx, rsp; StackCookie
0x18000aee6  call    __security_check_cookie
0x18000aeeb  lea     r11, [rsp+1E0h+var_20]
0x18000aef3  mov     rbx, [r11+30h]
0x18000aef7  mov     rsi, [r11+40h]
0x18000aefb  mov     rsp, r11
0x18000aefe  pop     r15
0x18000af00  pop     r14
0x18000af02  pop     r12
0x18000af04  pop     rdi
0x18000af05  pop     rbp
0x18000af06  retn
```
