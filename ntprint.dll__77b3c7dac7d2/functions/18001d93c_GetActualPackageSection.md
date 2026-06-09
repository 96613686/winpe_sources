# GetActualPackageSection

- ea: `0x18001d93c`
- end: `0x18001da80`
- name: `GetActualPackageSection`
- size: `324`
- prototype: ``
- caller_count: `5`
- callee_count: `6`
- tags: `installer_update`

## callers

- `0x180019818`
- `0x18001a914`
- `0x18001f1a4`
- `0x180020998`
- `0x18002ce44`

## callees

- `0x1800078f0`
- `0x180007944`
- `0x18000d57c`
- `0x18000d624`
- `0x18001d93c`
- `0x180035208`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d9c2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d9c2`

## string_xrefs

- `0x18001d9b3`: `Error building decorated package installation section name for decoration %ws: %!HRESULT!`
- `0x18001d9e4`: `Decorated package installation section name is %ws`
- `0x18001d96b`: `PrinterPackageInstallation`

## pseudocode

```c
__int64 __fastcall GetActualPackageSection(int a1, __int64 a2, unsigned __int16 *a3)
{
  __int64 v3; // rdi
  unsigned int v5; // ebx
  int v6; // eax
  DWORD LastError; // eax
  const unsigned __int16 *v8; // r9
  const unsigned __int16 *v9; // r8
  unsigned int v11; // [rsp+28h] [rbp-40h]
  unsigned int v12; // [rsp+30h] [rbp-38h]

  v3 = a1;
  if ( !a3 || !*(&PackageDecorations + a1) )
  {
    v5 = -2147024809;
    ClassInstallerTelemetry::WriteDbgTraceError(
      "GetActualPackageSection",
      L"Invalid Argument: platform=%ws, cchBufSize=%d, szSectionBuffer=%p",
      PlatformEnv[a1],
      40,
      a3);
    v12 = -2147024809;
    v9 = L"Invalid argument";
    v11 = 87;
    v8 = 0;
    goto LABEL_8;
  }
  v5 = StringCchCopyW(a3, 0x28u, L"PrinterPackageInstallation");
  if ( (v5 & 0x80000000) == 0 )
  {
    v6 = StringCchCatW(a3, 0x28u, (const unsigned __int16 *)*(&PackageDecorations + v3));
    v5 = v6;
    if ( v6 < 0 )
    {
      ClassInstallerTelemetry::WriteDbgTraceError(
        "GetActualPackageSection",
        L"Error building decorated package installation section name for decoration %ws: %!HRESULT!",
        *(&PackageDecorations + v3),
        (unsigned int)v6);
      LastError = GetLastError();
      v8 = (const unsigned __int16 *)*(&PackageDecorations + v3);
      v9 = L"StringCchCat failed (package decoration name in additional info)";
      v12 = v5;
      v11 = LastError;
LABEL_8:
      SplLogPrinterSetupGenericEvent(
        &SETUP_PRINTER_OPERATION_FAILED,
        L"GetActualPackageSection",
        v9,
        v8,
        (const unsigned __int16 *)PlatformEnv[v3],
        v11,
        v12);
      return v5;
    }
    ClassInstallerTelemetry::WriteDbgTraceInfo(
      "GetActualPackageSection",
      L"Decorated package installation section name is %ws",
      a3);
    SplLogPrinterSetupGenericEvent(
      &SETUP_PRINTER_OPERATION_SUCCEEDED,
      L"GetActualPackageSection",
      L"Decorated section name in additional info",
      a3,
      (const unsigned __int16 *)PlatformEnv[v3],
      0,
      v5);
  }
  return v5;
}

```

## disassembly

```asm
0x18001d93c  push    rbx
0x18001d93e  push    rsi
0x18001d93f  push    rdi
0x18001d940  push    r14
0x18001d942  sub     rsp, 48h
0x18001d946  movsxd  rdi, ecx
0x18001d949  mov     rsi, r8
0x18001d94c  lea     r14, __ImageBase
0x18001d953  test    r8, r8
0x18001d956  jz      loc_18001DA0F
0x18001d95c  cmp     rva ?PackageDecorations@@3PAU_SPLPLATFORMINFO@@A[r14+rdi*8], 0; _SPLPLATFORMINFO near * PackageDecorations ...
0x18001d965  jz      loc_18001DA0F
0x18001d96b  lea     r8, aPrinterpackage; "PrinterPackageInstallation"
0x18001d972  mov     edx, 28h ; '('; unsigned __int64
0x18001d977  mov     rcx, rsi; unsigned __int16 *
0x18001d97a  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18001d97f  mov     ebx, eax
0x18001d981  test    eax, eax
0x18001d983  js      loc_18001DA74
0x18001d989  mov     r8, rva ?PackageDecorations@@3PAU_SPLPLATFORMINFO@@A[r14+rdi*8]; unsigned __int16 *
0x18001d991  mov     edx, 28h ; '('; unsigned __int64
0x18001d996  mov     rcx, rsi; unsigned __int16 *
0x18001d999  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18001d99e  lea     rcx, aGetactualpacka_0; "GetActualPackageSection"
0x18001d9a5  mov     ebx, eax
0x18001d9a7  test    eax, eax
0x18001d9a9  jns     short loc_18001D9E1
0x18001d9ab  mov     r8, rva ?PackageDecorations@@3PAU_SPLPLATFORMINFO@@A[r14+rdi*8]; _SPLPLATFORMINFO near * PackageDecorations ...
0x18001d9b3  lea     rdx, aErrorBuildingD_2; "Error building decorated package instal"...
0x18001d9ba  mov     r9d, eax
0x18001d9bd  call    ?WriteDbgTraceError@ClassInstallerTelemetry@@SAXPEADPEAGZZ; ClassInstallerTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x18001d9c2  call    cs:__imp_GetLastError
0x18001d9c8  mov     r9, rva ?PackageDecorations@@3PAU_SPLPLATFORMINFO@@A[r14+rdi*8]; _SPLPLATFORMINFO near * PackageDecorations ...
0x18001d9d0  lea     r8, aStringcchcatFa; "StringCchCat failed (package decoration"...
0x18001d9d7  mov     [rsp+68h+var_38], ebx
0x18001d9db  mov     [rsp+68h+var_40], eax
0x18001d9df  jmp     short loc_18001DA54
0x18001d9e1  mov     r8, rsi
0x18001d9e4  lea     rdx, aDecoratedPacka; "Decorated package installation section "...
0x18001d9eb  call    ?WriteDbgTraceInfo@ClassInstallerTelemetry@@SAXPEADPEAGZZ; ClassInstallerTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x18001d9f0  mov     [rsp+68h+var_38], ebx
0x18001d9f4  lea     r8, aDecoratedSecti; "Decorated section name in additional in"...
0x18001d9fb  mov     [rsp+68h+var_40], 0
0x18001da03  lea     rcx, SETUP_PRINTER_OPERATION_SUCCEEDED
0x18001da0a  mov     r9, rsi
0x18001da0d  jmp     short loc_18001DA5B
0x18001da0f  mov     r8, rva PlatformEnv[r14+rdi*8]
0x18001da17  lea     rdx, aInvalidArgumen_17; "Invalid Argument: platform=%ws, cchBufS"...
0x18001da1e  mov     r9d, 28h ; '('
0x18001da24  mov     [rsp+68h+var_48], rsi
0x18001da29  lea     rcx, aGetactualpacka_0; "GetActualPackageSection"
0x18001da30  mov     ebx, 80070057h
0x18001da35  call    ?WriteDbgTraceError@ClassInstallerTelemetry@@SAXPEADPEAGZZ; ClassInstallerTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x18001da3a  mov     [rsp+68h+var_38], 80070057h; unsigned int
0x18001da42  lea     r8, aInvalidArgumen_1; "Invalid argument"
0x18001da49  mov     [rsp+68h+var_40], 57h ; 'W'; unsigned int
0x18001da51  xor     r9d, r9d; unsigned __int16 *
0x18001da54  lea     rcx, SETUP_PRINTER_OPERATION_FAILED; struct _EVENT_DESCRIPTOR *
0x18001da5b  mov     rax, rva PlatformEnv[r14+rdi*8]
0x18001da63  lea     rdx, aGetactualpacka_2; "GetActualPackageSection"
0x18001da6a  mov     [rsp+68h+var_48], rax; unsigned __int16 *
0x18001da6f  call    ?SplLogPrinterSetupGenericEvent@@YAXPEBU_EVENT_DESCRIPTOR@@PEBG111KK@Z; SplLogPrinterSetupGenericEvent(_EVENT_DESCRIPTOR const *,ushort const *,ushort const *,ushort const *,ushort const *,ulong,ulong)
0x18001da74  mov     eax, ebx
0x18001da76  add     rsp, 48h
0x18001da7a  pop     r14
0x18001da7c  pop     rdi
0x18001da7d  pop     rsi
0x18001da7e  pop     rbx
0x18001da7f  retn
```
