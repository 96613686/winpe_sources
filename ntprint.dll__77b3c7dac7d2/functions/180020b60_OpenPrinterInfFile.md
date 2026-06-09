# OpenPrinterInfFile

- ea: `0x180020b60`
- end: `0x180020c55`
- name: `OpenPrinterInfFile`
- size: `245`
- prototype: `__int64 __fastcall(unsigned __int16 *)`
- caller_count: `28`
- callee_count: `6`
- tags: `installer_update`

## callers

- `0x180009d64`
- `0x18000db80`
- `0x18000f698`
- `0x180013e68`
- `0x180015b84`
- `0x180017550`
- `0x18001785c`
- `0x180017d20`
- `0x180019818`
- `0x18001a1d8`
- `0x18001a454`
- `0x18001b160`
- `0x18001b320`
- `0x18001c680`
- `0x18001e07c`
- `0x18001e8b0`
- `0x18001f958`
- `0x180020998`
- `0x18002143c`
- `0x1800217e0`
- `0x18002cf10`
- `0x18002d608`
- `0x18002ffb4`
- `0x180030958`
- `0x180030c60`
- `0x180030e80`
- `0x180033f80`
- `0x1800340b4`

## callees

- `0x18000b200`
- `0x18000d57c`
- `0x18000d624`
- `0x180020b60`
- `0x180035208`
- `0x180036664`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180020c43`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180020c43`
- `SETUPAPI!SetupOpenInfFileW` at `0x180020bd6`
- `SETUPAPI!SetupOpenInfFileW` at `0x180020bd6`

## string_xrefs

- `0x180020baa`: `Opening printer INF file %ws (bIsLayoutInf=%ws)`
- `0x180020b7d`: `OpenPrinterInfFile`
- `0x180020c2e`: `OpenPrinterInfFile`
- `0x180020b93`: `Invalid Argument: pszInfPath=%ws, bIsLayoutInf=%ws`
- `0x180020bf3`: `SetupOpenInfFile failed`
- `0x180020c0c`: `OpenPrinterInfFile`
- `0x180020c24`: `Error opening %ws: hr: 0x%x`

## pseudocode

```c
__int64 __fastcall OpenPrinterInfFile(unsigned __int16 *a1, int a2)
{
  const wchar_t *v3; // r9
  __int64 v5; // rsi
  unsigned int v6; // ebx
  const WCHAR *v7; // rdx
  NCoreLibrary *v8; // rcx
  signed int LastErrorAsFailHR; // eax
  DWORD v10; // eax

  v3 = L"TRUE";
  if ( !a1 )
  {
    v5 = -1;
    v6 = -2147024809;
    if ( !a2 )
      v3 = L"FALSE";
    ClassInstallerTelemetry::WriteDbgTraceError(
      "OpenPrinterInfFile",
      L"Invalid Argument: pszInfPath=%ws, bIsLayoutInf=%ws",
      0,
      v3);
    goto LABEL_12;
  }
  if ( !a2 )
    v3 = L"FALSE";
  ClassInstallerTelemetry::WriteDbgTraceInfo(
    "OpenPrinterInfFile",
    L"Opening printer INF file %ws (bIsLayoutInf=%ws)",
    a1,
    v3);
  v7 = 0;
  if ( !a2 )
    v7 = L"Printer";
  v5 = (__int64)SetupOpenInfFileW(a1, v7, 0x42u, 0);
  if ( v5 == -1 )
  {
    LastErrorAsFailHR = NCoreLibrary::GetLastErrorAsFailHR(v8);
    v6 = LastErrorAsFailHR;
    if ( LastErrorAsFailHR < 0 )
    {
      SplLogPrinterSetupGenericEvent(
        &SETUP_PRINTER_OPERATION_FAILED,
        L"OpenPrinterInfFile",
        L"SetupOpenInfFile failed",
        a1,
        0,
        (unsigned __int16)LastErrorAsFailHR,
        LastErrorAsFailHR);
LABEL_12:
      ClassInstallerTelemetry::WriteDbgTraceError("OpenPrinterInfFile", L"Error opening %ws: hr: 0x%x", a1, v6);
      v10 = StatusFromHResult(v6);
      SetLastError(v10);
    }
  }
  return v5;
}

```

## disassembly

```asm
0x180020b60  push    rbx
0x180020b62  push    rbp
0x180020b63  push    rsi
0x180020b64  push    rdi
0x180020b65  sub     rsp, 48h
0x180020b69  mov     rdi, rcx
0x180020b6c  lea     rax, aFalse_0; "FALSE"
0x180020b73  test    rcx, rcx
0x180020b76  lea     r9, aTrue_0; "TRUE"
0x180020b7d  lea     rcx, aOpenprinterinf_0; "OpenPrinterInfFile"
0x180020b84  mov     ebp, edx
0x180020b86  jnz     short loc_180020BA8
0x180020b88  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180020b8c  mov     ebx, 80070057h
0x180020b91  test    edx, edx
0x180020b93  lea     rdx, aInvalidArgumen_18; "Invalid Argument: pszInfPath=%ws, bIsLa"...
0x180020b9a  cmovz   r9, rax
0x180020b9e  xor     r8d, r8d
0x180020ba1  call    ?WriteDbgTraceError@ClassInstallerTelemetry@@SAXPEADPEAGZZ; ClassInstallerTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x180020ba6  jmp     short loc_180020C21
0x180020ba8  test    ebp, ebp
0x180020baa  lea     rdx, aOpeningPrinter; "Opening printer INF file %ws (bIsLayout"...
0x180020bb1  mov     r8, rdi
0x180020bb4  cmovz   r9, rax
0x180020bb8  call    ?WriteDbgTraceInfo@ClassInstallerTelemetry@@SAXPEADPEAGZZ; ClassInstallerTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x180020bbd  xor     edx, edx
0x180020bbf  lea     rax, cszPrinter; "Printer"
0x180020bc6  test    ebp, ebp
0x180020bc8  mov     rcx, rdi; FileName
0x180020bcb  cmovz   rdx, rax; InfClass
0x180020bcf  xor     r9d, r9d; ErrorLine
0x180020bd2  lea     r8d, [r9+42h]; InfStyle
0x180020bd6  call    cs:__imp_SetupOpenInfFileW
0x180020bdc  mov     rsi, rax
0x180020bdf  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180020be3  jnz     short loc_180020C49
0x180020be5  call    ?GetLastErrorAsFailHR@NCoreLibrary@@YAJXZ; NCoreLibrary::GetLastErrorAsFailHR(void)
0x180020bea  mov     ebx, eax
0x180020bec  test    eax, eax
0x180020bee  jns     short loc_180020C49
0x180020bf0  movzx   edx, ax
0x180020bf3  lea     r8, aSetupopeninffi; "SetupOpenInfFile failed"
0x180020bfa  mov     [rsp+68h+var_38], eax; unsigned int
0x180020bfe  lea     rcx, SETUP_PRINTER_OPERATION_FAILED; struct _EVENT_DESCRIPTOR *
0x180020c05  mov     [rsp+68h+var_40], edx; unsigned int
0x180020c09  mov     r9, rdi; unsigned __int16 *
0x180020c0c  lea     rdx, aOpenprinterinf_2; "OpenPrinterInfFile"
0x180020c13  mov     [rsp+68h+var_48], 0; unsigned __int16 *
0x180020c1c  call    ?SplLogPrinterSetupGenericEvent@@YAXPEBU_EVENT_DESCRIPTOR@@PEBG111KK@Z; SplLogPrinterSetupGenericEvent(_EVENT_DESCRIPTOR const *,ushort const *,ushort const *,ushort const *,ushort const *,ulong,ulong)
0x180020c21  mov     r9d, ebx
0x180020c24  lea     rdx, aErrorOpeningWs; "Error opening %ws: hr: 0x%x"
0x180020c2b  mov     r8, rdi
0x180020c2e  lea     rcx, aOpenprinterinf_0; "OpenPrinterInfFile"
0x180020c35  call    ?WriteDbgTraceError@ClassInstallerTelemetry@@SAXPEADPEAGZZ; ClassInstallerTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x180020c3a  mov     ecx, ebx
0x180020c3c  call    StatusFromHResult
0x180020c41  mov     ecx, eax; dwErrCode
0x180020c43  call    cs:__imp_SetLastError
0x180020c49  mov     rax, rsi
0x180020c4c  add     rsp, 48h
0x180020c50  pop     rdi
0x180020c51  pop     rsi
0x180020c52  pop     rbp
0x180020c53  pop     rbx
0x180020c54  retn
```
