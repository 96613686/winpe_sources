# UpdateDriverForInstalledConnection(_PSETUP_LOCAL_DATA *,ushort *)

- ea: `0x180015e6c`
- end: `0x180016021`
- name: `?UpdateDriverForInstalledConnection@@YAKPEAU_PSETUP_LOCAL_DATA@@PEAG@Z`
- size: `437`
- prototype: `unsigned int(struct _PSETUP_LOCAL_DATA *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `3`
- tags: `installer_update`

## callers

- `0x180013804`

## callees

- `0x18000d57c`
- `0x18000d624`
- `0x180015e6c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015efb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015f6a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015f89`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015f93`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015fb2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015fca`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015fe9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015efb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015f6a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015f89`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015f93`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015fb2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015fca`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015fe9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180015fc2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180015fc2`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180015f10`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180015f10`
- `WINSPOOL!SetPrinterW` at `0x180015f60`
- `WINSPOOL!SetPrinterW` at `0x180015f60`
- `WINSPOOL!GetPrinterW` at `0x180015eed`
- `WINSPOOL!GetPrinterW` at `0x180015f37`
- `WINSPOOL!GetPrinterW` at `0x180015eed`
- `WINSPOOL!GetPrinterW` at `0x180015f37`
- `WINSPOOL!OpenPrinterW` at `0x180015eab`
- `WINSPOOL!OpenPrinterW` at `0x180015eab`
- `WINSPOOL!ClosePrinter` at `0x180015ff5`
- `WINSPOOL!ClosePrinter` at `0x180015ff5`

## string_xrefs

- `0x180015ec3`: `CSR GUID Printer '%ws' exists, will update driver.`
- `0x180015eb4`: `UpdateDriverForInstalledConnection`
- `0x180015f7d`: `UpdateDriverForInstalledConnection`
- `0x180015fa6`: `UpdateDriverForInstalledConnection`
- `0x180015fdd`: `UpdateDriverForInstalledConnection`
- `0x180015f73`: `Failed to update driver for GUID printer '%ws'.  Error %d`

## pseudocode

```c
__int64 __fastcall UpdateDriverForInstalledConnection(struct _PSETUP_LOCAL_DATA *a1, unsigned __int16 *a2)
{
  BYTE *v4; // rbx
  DWORD v5; // edi
  DWORD v6; // eax
  DWORD v7; // eax
  DWORD LastError; // eax
  struct _PRINTER_DEFAULTSW pDefault; // [rsp+30h] [rbp-20h] BYREF
  DWORD cbBuf; // [rsp+80h] [rbp+30h] BYREF
  HANDLE phPrinter; // [rsp+88h] [rbp+38h] BYREF

  *(_QWORD *)&pDefault.DesiredAccess = 983052;
  phPrinter = 0;
  *(_OWORD *)&pDefault.pDatatype = 0;
  if ( !OpenPrinterW(a2, &phPrinter, &pDefault) )
  {
    ClassInstallerTelemetry::WriteDbgTraceInfo(
      "UpdateDriverForInstalledConnection",
      L"CSR GUID Printer '%ws' does not exist.  Assuming CSR connection in progress.",
      a2);
    return 0;
  }
  ClassInstallerTelemetry::WriteDbgTraceInfo(
    "UpdateDriverForInstalledConnection",
    L"CSR GUID Printer '%ws' exists, will update driver.",
    a2);
  cbBuf = 0;
  if ( GetPrinterW(phPrinter, 2u, 0, 0, &cbBuf) || GetLastError() != 122 )
  {
    LastError = GetLastError();
    ClassInstallerTelemetry::WriteDbgTraceError(
      "UpdateDriverForInstalledConnection",
      L"Failed to get info about GUID printer '%ws'.  Error %d",
      a2,
      LastError);
    v5 = GetLastError();
    goto LABEL_11;
  }
  v4 = (BYTE *)LocalAlloc(0x40u, cbBuf);
  if ( v4 && GetPrinterW(phPrinter, 2u, v4, cbBuf, &cbBuf) )
  {
    v5 = 0;
    *((_QWORD *)v4 + 4) = *((_QWORD *)a1 + 1);
    *((_QWORD *)v4 + 9) = 0;
    *((_QWORD *)v4 + 10) = 0;
    if ( !SetPrinterW(phPrinter, 2u, v4, 0) )
    {
      v6 = GetLastError();
      ClassInstallerTelemetry::WriteDbgTraceError(
        "UpdateDriverForInstalledConnection",
        L"Failed to update driver for GUID printer '%ws'.  Error %d",
        a2,
        v6);
      v5 = GetLastError();
    }
    goto LABEL_9;
  }
  v7 = GetLastError();
  ClassInstallerTelemetry::WriteDbgTraceError(
    "UpdateDriverForInstalledConnection",
    L"Failed to get info about GUID printer '%ws'.  Error %d",
    a2,
    v7);
  v5 = GetLastError();
  if ( v4 )
LABEL_9:
    LocalFree(v4);
LABEL_11:
  ClosePrinter(phPrinter);
  return v5;
}

```

## disassembly

```asm
0x180015e6c  mov     [rsp-18h+arg_0], rbx
0x180015e71  mov     [rsp-18h+arg_8], rdi
0x180015e76  push    rbp
0x180015e77  push    r14
0x180015e79  push    r15
0x180015e7b  mov     rbp, rsp
0x180015e7e  sub     rsp, 50h
0x180015e82  mov     r14, rdx
0x180015e85  mov     qword ptr [rbp+pDefault.DesiredAccess], 0F000Ch
0x180015e8d  mov     r15, rcx
0x180015e90  mov     [rbp+phPrinter], 0
0x180015e98  xorps   xmm0, xmm0
0x180015e9b  lea     r8, [rbp+pDefault]; pDefault
0x180015e9f  mov     rcx, r14; pPrinterName
0x180015ea2  lea     rdx, [rbp+phPrinter]; phPrinter
0x180015ea6  movdqu  xmmword ptr [rbp+pDefault.pDatatype], xmm0
0x180015eab  call    cs:__imp_OpenPrinterW
0x180015eb1  mov     r8, r14
0x180015eb4  lea     rcx, aUpdatedriverfo; "UpdateDriverForInstalledConnection"
0x180015ebb  test    eax, eax
0x180015ebd  jz      loc_180015FFD
0x180015ec3  lea     rdx, aCsrGuidPrinter; "CSR GUID Printer '%ws' exists, will upd"...
0x180015eca  call    ?WriteDbgTraceInfo@ClassInstallerTelemetry@@SAXPEADPEAGZZ; ClassInstallerTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x180015ecf  mov     rcx, [rbp+phPrinter]; hPrinter
0x180015ed3  lea     rax, [rbp+cbBuf]
0x180015ed7  xor     r9d, r9d; cbBuf
0x180015eda  mov     [rbp+cbBuf], 0
0x180015ee1  xor     r8d, r8d; pPrinter
0x180015ee4  mov     [rsp+50h+pcbNeeded], rax; pcbNeeded
0x180015ee9  lea     edx, [r9+2]; Level
0x180015eed  call    cs:__imp_GetPrinterW
0x180015ef3  test    eax, eax
0x180015ef5  jnz     loc_180015FCA
0x180015efb  call    cs:__imp_GetLastError
0x180015f01  cmp     eax, 7Ah ; 'z'
0x180015f04  jnz     loc_180015FCA
0x180015f0a  mov     edx, [rbp+cbBuf]; uBytes
0x180015f0d  lea     ecx, [rax-3Ah]; uFlags
0x180015f10  call    cs:__imp_LocalAlloc
0x180015f16  mov     rbx, rax
0x180015f19  test    rax, rax
0x180015f1c  jz      short loc_180015F93
0x180015f1e  mov     r9d, [rbp+cbBuf]; cbBuf
0x180015f22  lea     rax, [rbp+cbBuf]
0x180015f26  mov     rcx, [rbp+phPrinter]; hPrinter
0x180015f2a  mov     r8, rbx; pPrinter
0x180015f2d  mov     edx, 2; Level
0x180015f32  mov     [rsp+50h+pcbNeeded], rax; pcbNeeded
0x180015f37  call    cs:__imp_GetPrinterW
0x180015f3d  test    eax, eax
0x180015f3f  jz      short loc_180015F93
0x180015f41  mov     rax, [r15+8]
0x180015f45  xor     edi, edi
0x180015f47  mov     [rbx+20h], rax
0x180015f4b  xor     r9d, r9d; Command
0x180015f4e  mov     [rbx+48h], rdi
0x180015f52  mov     r8, rbx; pPrinter
0x180015f55  mov     [rbx+50h], rdi
0x180015f59  mov     rcx, [rbp+phPrinter]; hPrinter
0x180015f5d  lea     edx, [rdi+2]; Level
0x180015f60  call    cs:__imp_SetPrinterW
0x180015f66  test    eax, eax
0x180015f68  jnz     short loc_180015FBF
0x180015f6a  call    cs:__imp_GetLastError
0x180015f70  mov     r8, r14
0x180015f73  lea     rdx, aFailedToUpdate; "Failed to update driver for GUID printe"...
0x180015f7a  mov     r9d, eax
0x180015f7d  lea     rcx, aUpdatedriverfo; "UpdateDriverForInstalledConnection"
0x180015f84  call    ?WriteDbgTraceError@ClassInstallerTelemetry@@SAXPEADPEAGZZ; ClassInstallerTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x180015f89  call    cs:__imp_GetLastError
0x180015f8f  mov     edi, eax
0x180015f91  jmp     short loc_180015FBF
0x180015f93  call    cs:__imp_GetLastError
0x180015f99  mov     r8, r14
0x180015f9c  lea     rdx, aFailedToGetInf; "Failed to get info about GUID printer '"...
0x180015fa3  mov     r9d, eax
0x180015fa6  lea     rcx, aUpdatedriverfo; "UpdateDriverForInstalledConnection"
0x180015fad  call    ?WriteDbgTraceError@ClassInstallerTelemetry@@SAXPEADPEAGZZ; ClassInstallerTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x180015fb2  call    cs:__imp_GetLastError
0x180015fb8  mov     edi, eax
0x180015fba  test    rbx, rbx
0x180015fbd  jz      short loc_180015FF1
0x180015fbf  mov     rcx, rbx; hMem
0x180015fc2  call    cs:__imp_LocalFree
0x180015fc8  jmp     short loc_180015FF1
0x180015fca  call    cs:__imp_GetLastError
0x180015fd0  mov     r8, r14
0x180015fd3  lea     rdx, aFailedToGetInf; "Failed to get info about GUID printer '"...
0x180015fda  mov     r9d, eax
0x180015fdd  lea     rcx, aUpdatedriverfo; "UpdateDriverForInstalledConnection"
0x180015fe4  call    ?WriteDbgTraceError@ClassInstallerTelemetry@@SAXPEADPEAGZZ; ClassInstallerTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x180015fe9  call    cs:__imp_GetLastError
0x180015fef  mov     edi, eax
0x180015ff1  mov     rcx, [rbp+phPrinter]; hPrinter
0x180015ff5  call    cs:__imp_ClosePrinter
0x180015ffb  jmp     short loc_18001600B
0x180015ffd  lea     rdx, aCsrGuidPrinter_0; "CSR GUID Printer '%ws' does not exist. "...
0x180016004  call    ?WriteDbgTraceInfo@ClassInstallerTelemetry@@SAXPEADPEAGZZ; ClassInstallerTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x180016009  xor     edi, edi
0x18001600b  mov     rbx, [rsp+50h+arg_0]
0x180016010  mov     eax, edi
0x180016012  mov     rdi, [rsp+50h+arg_8]
0x180016017  add     rsp, 50h
0x18001601b  pop     r15
0x18001601d  pop     r14
0x18001601f  pop     rbp
0x180016020  retn
```
