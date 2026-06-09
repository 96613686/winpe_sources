# InstallPrintToPDFDriverViaBroker(ushort *,ulong *)

- ea: `0x1800c7dc4`
- end: `0x1800c7f8e`
- name: `?InstallPrintToPDFDriverViaBroker@@YAJPEAGPEAK@Z`
- size: `458`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned int *)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180077284`

## callees

- `0x180011f00`
- `0x18002ff50`
- `0x18003ea2c`
- `0x1800c72e4`
- `0x1800c7c1c`
- `0x1800c7dc4`
- `0x1800e6010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800c7ec2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800c7ed3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800c7ef8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800c7ec2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800c7ed3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800c7ef8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c7e95`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c7f5b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c7e95`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c7f5b`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x1800c7de1`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x1800c7de1`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1800c7f75`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1800c7f75`

## string_xrefs

- `0x1800c7e42`: `GetPrintScanBroker failed. Error 0x%x`
- `0x1800c7f15`: `StringCchCopy failed. Error 0x%x`
- `0x1800c7f37`: `destInfPathHString.GetRawBuffer failed. Error 0x%x`
- `0x1800c7e06`: `InstallPrintToPDFDriverViaBroker`
- `0x1800c7e4c`: `InstallPrintToPDFDriverViaBroker`
- `0x1800c7f4a`: `InstallPrintToPDFDriverViaBroker`
- `0x1800c7f40`: `InstallPrintToPDFDriver failed. Error 0x%x`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall InstallPrintToPDFDriverViaBroker(unsigned __int16 *a1, unsigned int *a2)
{
  HRESULT PrintScanBroker; // ebx
  __int64 v5; // rdi
  __int64 (__fastcall *v6)(__int64, _QWORD, HSTRING *); // rbx
  int v7; // eax
  PCWSTR StringRawBuffer; // rax
  __int64 v9; // rcx
  unsigned int v10; // edi
  const unsigned __int16 *v11; // rax
  unsigned __int16 *v12; // rdx
  HSTRING string; // [rsp+20h] [rbp-20h] BYREF
  _QWORD v15[2]; // [rsp+28h] [rbp-18h] BYREF
  char v16; // [rsp+38h] [rbp-8h]
  bool v17; // [rsp+80h] [rbp+40h] BYREF
  unsigned __int16 v18; // [rsp+88h] [rbp+48h] BYREF

  PrintScanBroker = CoInitializeEx(0, 0);
  if ( (int)(PrintScanBroker + 0x80000000) >= 0 && PrintScanBroker != -2147417850 )
  {
    LocalSpoolerTelemetry::WriteDbgTraceError(
      "InstallPrintToPDFDriverViaBroker",
      L"CoInitializeEx failed. Error 0x%x",
      (unsigned int)PrintScanBroker);
    return (unsigned int)PrintScanBroker;
  }
  v17 = PrintScanBroker >= 0;
  v15[1] = &v17;
  v16 = 1;
  v15[0] = 0;
  PrintScanBroker = GetPrintScanBroker(v15);
  if ( PrintScanBroker >= 0 )
  {
    v18 = 0;
    PrintScanBroker = GetProcessorArchitectureFromEnvironmentString(L"Windows x64", &v18);
    if ( PrintScanBroker < 0 )
    {
      LocalSpoolerTelemetry::WriteDbgTraceError(
        "InstallPrintToPDFDriverViaBroker",
        L"GetProcessorArchitectureFromEnvironmentString failed. Error 0x%x",
        (unsigned int)PrintScanBroker);
      goto LABEL_22;
    }
    string = 0;
    v5 = v15[0];
    v6 = *(__int64 (__fastcall **)(__int64, _QWORD, HSTRING *))(*(_QWORD *)v15[0] + 144LL);
    WindowsDeleteString(0);
    string = 0;
    v7 = v6(v5, v18, &string);
    PrintScanBroker = v7;
    if ( v7 < 0 )
    {
      v12 = L"InstallPrintToPDFDriver failed. Error 0x%x";
    }
    else
    {
      if ( !WindowsGetStringRawBuffer(string, 0) )
      {
        PrintScanBroker = -2147418113;
        LocalSpoolerTelemetry::WriteDbgTraceError(
          "InstallPrintToPDFDriverViaBroker",
          L"destInfPathHString.GetRawBuffer failed. Error 0x%x",
          2147549183LL);
        goto LABEL_21;
      }
      StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
      v9 = -1;
      do
        ++v9;
      while ( StringRawBuffer[v9] );
      v10 = v9 + 1;
      if ( v9 + 1 > (unsigned __int64)*a2 )
      {
        PrintScanBroker = -2147024774;
        LocalSpoolerTelemetry::WriteDbgTraceError(
          "InstallPrintToPDFDriverViaBroker",
          L"Buffer too small. Error 0x%x",
          2147942522LL);
        goto LABEL_21;
      }
      v11 = WindowsGetStringRawBuffer(string, 0);
      v7 = StringCchCopyW(a1, *a2, v11);
      PrintScanBroker = v7;
      if ( v7 >= 0 )
      {
        *a2 = v10;
LABEL_21:
        WindowsDeleteString(string);
        string = 0;
        goto LABEL_22;
      }
      v12 = L"StringCchCopy failed. Error 0x%x";
    }
    LocalSpoolerTelemetry::WriteDbgTraceError("InstallPrintToPDFDriverViaBroker", v12, (unsigned int)v7);
    goto LABEL_21;
  }
  LocalSpoolerTelemetry::WriteDbgTraceError(
    "InstallPrintToPDFDriverViaBroker",
    L"GetPrintScanBroker failed. Error 0x%x",
    (unsigned int)PrintScanBroker);
LABEL_22:
  wil::com_ptr_t<Windows::Graphics::Internal::Printing::PrintScanBroker::IPrintScanBrokerHandler,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Internal::Printing::PrintScanBroker::IPrintScanBrokerHandler,wil::err_returncode_policy>(v15);
  if ( v17 )
    CoUninitialize();
  return (unsigned int)PrintScanBroker;
}

```

## disassembly

```asm
0x1800c7dc4  mov     [rsp-28h+arg_0], rbx
0x1800c7dc9  push    rbp
0x1800c7dca  push    rsi
0x1800c7dcb  push    rdi
0x1800c7dcc  push    r14
0x1800c7dce  push    r15
0x1800c7dd0  mov     rbp, rsp
0x1800c7dd3  sub     rsp, 40h
0x1800c7dd7  mov     rsi, rdx
0x1800c7dda  mov     r14, rcx
0x1800c7ddd  xor     edx, edx; dwCoInit
0x1800c7ddf  xor     ecx, ecx; pvReserved
0x1800c7de1  call    cs:__imp_CoInitializeEx
0x1800c7de7  mov     ebx, eax
0x1800c7de9  mov     ecx, 80000000h
0x1800c7dee  add     eax, ecx
0x1800c7df0  test    ecx, eax
0x1800c7df2  jnz     short loc_1800C7E17
0x1800c7df4  cmp     ebx, 80010106h
0x1800c7dfa  jz      short loc_1800C7E17
0x1800c7dfc  mov     r8d, ebx
0x1800c7dff  lea     rdx, aCoinitializeex_0; "CoInitializeEx failed. Error 0x%x"
0x1800c7e06  lea     rcx, aInstallprintto; "InstallPrintToPDFDriverViaBroker"
0x1800c7e0d  call    ?WriteDbgTraceError@LocalSpoolerTelemetry@@SAXPEADPEAGZZ; LocalSpoolerTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x1800c7e12  jmp     loc_1800C7F7B
0x1800c7e17  shr     ebx, 1Fh
0x1800c7e1a  xor     bl, 1
0x1800c7e1d  mov     [rbp+arg_10], bl
0x1800c7e20  lea     rax, [rbp+arg_10]
0x1800c7e24  mov     [rbp+var_10], rax
0x1800c7e28  mov     [rbp+var_8], 1
0x1800c7e2c  xor     r15d, r15d
0x1800c7e2f  mov     [rbp+var_18], r15
0x1800c7e33  lea     rcx, [rbp+var_18]
0x1800c7e37  call    ?GetPrintScanBroker@@YAJAEAV?$com_ptr_t@UIPrintScanBrokerHandler@PrintScanBroker@Printing@Internal@Graphics@Windows@@Uerr_returncode_policy@wil@@@wil@@@Z; GetPrintScanBroker(wil::com_ptr_t<Windows::Graphics::Internal::Printing::PrintScanBroker::IPrintScanBrokerHandler,wil::err_returncode_policy> &)
0x1800c7e3c  mov     ebx, eax
0x1800c7e3e  test    eax, eax
0x1800c7e40  jns     short loc_1800C7E5D
0x1800c7e42  lea     rdx, aGetprintscanbr; "GetPrintScanBroker failed. Error 0x%x"
0x1800c7e49  mov     r8d, ebx
0x1800c7e4c  lea     rcx, aInstallprintto; "InstallPrintToPDFDriverViaBroker"
0x1800c7e53  call    ?WriteDbgTraceError@LocalSpoolerTelemetry@@SAXPEADPEAGZZ; LocalSpoolerTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x1800c7e58  jmp     loc_1800C7F65
0x1800c7e5d  mov     [rbp+arg_18], r15w
0x1800c7e62  lea     rdx, [rbp+arg_18]
0x1800c7e66  lea     rcx, aWindowsX64_0; "Windows x64"
0x1800c7e6d  call    GetProcessorArchitectureFromEnvironmentString
0x1800c7e72  mov     ebx, eax
0x1800c7e74  test    eax, eax
0x1800c7e76  jns     short loc_1800C7E81
0x1800c7e78  lea     rdx, aGetprocessorar_0; "GetProcessorArchitectureFromEnvironment"...
0x1800c7e7f  jmp     short loc_1800C7E49
0x1800c7e81  mov     [rbp+string], r15
0x1800c7e85  mov     rdi, [rbp+var_18]
0x1800c7e89  mov     rax, [rdi]
0x1800c7e8c  mov     rbx, [rax+90h]
0x1800c7e93  xor     ecx, ecx; string
0x1800c7e95  call    cs:__imp_WindowsDeleteString
0x1800c7e9b  mov     [rbp+string], r15
0x1800c7e9f  lea     r8, [rbp+string]
0x1800c7ea3  movzx   edx, [rbp+arg_18]
0x1800c7ea7  mov     rcx, rdi
0x1800c7eaa  mov     rax, rbx
0x1800c7ead  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c7eb2  mov     ebx, eax
0x1800c7eb4  test    eax, eax
0x1800c7eb6  js      loc_1800C7F40
0x1800c7ebc  xor     edx, edx; length
0x1800c7ebe  mov     rcx, [rbp+string]; string
0x1800c7ec2  call    cs:__imp_WindowsGetStringRawBuffer
0x1800c7ec8  test    rax, rax
0x1800c7ecb  jz      short loc_1800C7F2F
0x1800c7ecd  xor     edx, edx; length
0x1800c7ecf  mov     rcx, [rbp+string]; string
0x1800c7ed3  call    cs:__imp_WindowsGetStringRawBuffer
0x1800c7ed9  or      rcx, 0FFFFFFFFFFFFFFFFh
0x1800c7edd  inc     rcx
0x1800c7ee0  cmp     [rax+rcx*2], r15w
0x1800c7ee5  jnz     short loc_1800C7EDD
0x1800c7ee7  lea     rdi, [rcx+1]
0x1800c7eeb  mov     eax, [rsi]
0x1800c7eed  cmp     rdi, rax
0x1800c7ef0  ja      short loc_1800C7F1E
0x1800c7ef2  xor     edx, edx; length
0x1800c7ef4  mov     rcx, [rbp+string]; string
0x1800c7ef8  call    cs:__imp_WindowsGetStringRawBuffer
0x1800c7efe  mov     edx, [rsi]; unsigned __int64
0x1800c7f00  mov     r8, rax; unsigned __int16 *
0x1800c7f03  mov     rcx, r14; unsigned __int16 *
0x1800c7f06  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800c7f0b  mov     ebx, eax
0x1800c7f0d  test    eax, eax
0x1800c7f0f  js      short loc_1800C7F15
0x1800c7f11  mov     [rsi], edi
0x1800c7f13  jmp     short loc_1800C7F57
0x1800c7f15  lea     rdx, aStringcchcopyF; "StringCchCopy failed. Error 0x%x"
0x1800c7f1c  jmp     short loc_1800C7F47
0x1800c7f1e  mov     ebx, 8007007Ah
0x1800c7f23  mov     r8d, ebx
0x1800c7f26  lea     rdx, aBufferTooSmall; "Buffer too small. Error 0x%x"
0x1800c7f2d  jmp     short loc_1800C7F4A
0x1800c7f2f  mov     ebx, 8000FFFFh
0x1800c7f34  mov     r8d, ebx
0x1800c7f37  lea     rdx, aDestinfpathhst; "destInfPathHString.GetRawBuffer failed."...
0x1800c7f3e  jmp     short loc_1800C7F4A
0x1800c7f40  lea     rdx, aInstallprintto_0; "InstallPrintToPDFDriver failed. Error 0"...
0x1800c7f47  mov     r8d, eax
0x1800c7f4a  lea     rcx, aInstallprintto; "InstallPrintToPDFDriverViaBroker"
0x1800c7f51  call    ?WriteDbgTraceError@LocalSpoolerTelemetry@@SAXPEADPEAGZZ; LocalSpoolerTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x1800c7f56  nop
0x1800c7f57  mov     rcx, [rbp+string]; string
0x1800c7f5b  call    cs:__imp_WindowsDeleteString
0x1800c7f61  mov     [rbp+string], r15
0x1800c7f65  lea     rcx, [rbp+var_18]
0x1800c7f69  call    ??1?$com_ptr_t@UIPrintScanBrokerHandler@PrintScanBroker@Printing@Internal@Graphics@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Graphics::Internal::Printing::PrintScanBroker::IPrintScanBrokerHandler,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Internal::Printing::PrintScanBroker::IPrintScanBrokerHandler,wil::err_returncode_policy>(void)
0x1800c7f6e  nop
0x1800c7f6f  cmp     [rbp+arg_10], r15b
0x1800c7f73  jz      short loc_1800C7F7B
0x1800c7f75  call    cs:__imp_CoUninitialize
0x1800c7f7b  mov     eax, ebx
0x1800c7f7d  mov     rbx, [rsp+40h+arg_0]
0x1800c7f82  add     rsp, 40h
0x1800c7f86  pop     r15
0x1800c7f88  pop     r14
0x1800c7f8a  pop     rdi
0x1800c7f8b  pop     rsi
0x1800c7f8c  pop     rbp
0x1800c7f8d  retn
```
