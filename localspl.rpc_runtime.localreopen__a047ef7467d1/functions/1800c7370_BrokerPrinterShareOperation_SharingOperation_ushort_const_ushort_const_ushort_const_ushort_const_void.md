# BrokerPrinterShareOperation(SharingOperation,ushort const *,ushort const *,ushort const *,ushort const *,void *)

- ea: `0x1800c7370`
- end: `0x1800c7741`
- name: `?BrokerPrinterShareOperation@@YAJW4SharingOperation@@PEBG111PEAX@Z`
- size: `977`
- prototype: ``
- caller_count: `3`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180077e28`
- `0x1800932c8`
- `0x1800939e8`

## callees

- `0x18003ea2c`
- `0x1800c72e4`
- `0x1800c7370`
- `0x1800c7c1c`
- `0x1800c7d10`
- `0x1800e6010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c7444`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c7444`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800c7712`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800c7712`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c74c1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c751e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c752c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c75ca`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c75db`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c75e9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c75f7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c7605`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c76a3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c76b4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c76c2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c76d0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c76de`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c74c1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c751e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c752c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c75ca`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c75db`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c75e9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c75f7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c7605`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c76a3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c76b4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c76c2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c76d0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c76de`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x1800c739e`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x1800c739e`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1800c771e`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1800c771e`
- `api-ms-win-security-sddl-l1-1-0!ConvertSecurityDescriptorToStringSecurityDescriptorW` at `0x1800c743a`
- `api-ms-win-security-sddl-l1-1-0!ConvertSecurityDescriptorToStringSecurityDescriptorW` at `0x1800c743a`

## string_xrefs

- `0x1800c740b`: `GetPrintScanBroker failed. Error 0x%x`
- `0x1800c73c3`: `BrokerPrinterShareOperation`
- `0x1800c76f2`: `BrokerPrinterShareOperation`
- `0x1800c7459`: `ConvertSecurityDescriptorToStringSecurityDescriptor failed. Error 0x%x`
- `0x1800c7613`: `UpdatePrinterShare failed. Error 0x%x`

## pseudocode

```c
// Hidden C++ exception states: #wind=13
__int64 __fastcall BrokerPrinterShareOperation(
        int a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        PSECURITY_DESCRIPTOR SecurityDescriptor)
{
  int PrintScanBroker; // ebx
  signed int LastError; // eax
  int v10; // edi
  int v11; // edi
  __int64 v12; // rdi
  __int64 (__fastcall *v13)(__int64, _QWORD); // rbx
  _QWORD *v14; // rax
  __int64 v15; // rsi
  __int64 (__fastcall *v16)(__int64, _QWORD, __int64); // rdi
  __int64 v17; // rbx
  _QWORD *v18; // rax
  __int64 v19; // r12
  __int64 (__fastcall *v20)(__int64, _QWORD, __int64, __int64, __int64, __int64); // r15
  __int64 v21; // r14
  __int64 v22; // rsi
  __int64 v23; // rdi
  __int64 v24; // rbx
  _QWORD *v25; // rax
  __int64 v26; // r12
  __int64 (__fastcall *v27)(__int64, _QWORD, __int64, __int64, __int64, __int64); // r15
  __int64 v28; // r14
  __int64 v29; // rsi
  __int64 v30; // rdi
  __int64 v31; // rbx
  _QWORD *v32; // rax
  bool v34; // [rsp+48h] [rbp-49h] BYREF
  ULONG StringSecurityDescriptorLen[2]; // [rsp+50h] [rbp-41h] BYREF
  HSTRING string; // [rsp+58h] [rbp-39h] BYREF
  __int64 v37; // [rsp+60h] [rbp-31h] BYREF
  LPWSTR StringSecurityDescriptor; // [rsp+68h] [rbp-29h] BYREF
  HSTRING v39; // [rsp+70h] [rbp-21h] BYREF
  HSTRING v40; // [rsp+78h] [rbp-19h] BYREF
  HSTRING v41[3]; // [rsp+80h] [rbp-11h] BYREF
  char v42; // [rsp+98h] [rbp+7h]

  PrintScanBroker = CoInitializeEx(0, 0);
  if ( (int)(PrintScanBroker + 0x80000000) < 0 || PrintScanBroker == -2147417850 )
  {
    v34 = PrintScanBroker >= 0;
    StringSecurityDescriptor = 0;
    v41[1] = (HSTRING)&StringSecurityDescriptor;
    v41[2] = (HSTRING)&v34;
    v42 = 1;
    v37 = 0;
    PrintScanBroker = GetPrintScanBroker(&v37);
    if ( PrintScanBroker >= 0 )
    {
      if ( !SecurityDescriptor
        || (StringSecurityDescriptorLen[0] = 0,
            ConvertSecurityDescriptorToStringSecurityDescriptorW(
              SecurityDescriptor,
              1u,
              7u,
              &StringSecurityDescriptor,
              StringSecurityDescriptorLen)) )
      {
        if ( a1 )
        {
          v10 = a1 - 1;
          if ( v10 )
          {
            v11 = v10 - 1;
            if ( v11 )
            {
              if ( v11 == 1 )
              {
                v12 = v37;
                v13 = *(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v37 + 216LL);
                v14 = (_QWORD *)HStringWrapper(&string, a5);
                PrintScanBroker = v13(v12, *v14);
                WindowsDeleteString(string);
                if ( PrintScanBroker < 0 )
                  LocalSpoolerTelemetry::WriteDbgTraceError(
                    "BrokerPrinterShareOperation",
                    L"UnshareAllPrinters failed. Error 0x%x",
                    (unsigned int)PrintScanBroker);
              }
              else
              {
                PrintScanBroker = -2147024809;
                LocalSpoolerTelemetry::WriteDbgTraceError(
                  "BrokerPrinterShareOperation",
                  L"Invalid SharingOperation. Error 0x%x",
                  2147942487LL);
              }
            }
            else
            {
              v15 = v37;
              v16 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64))(*(_QWORD *)v37 + 208LL);
              v17 = *(_QWORD *)HStringWrapper(&string, a5);
              v18 = (_QWORD *)HStringWrapper(StringSecurityDescriptorLen, a2);
              PrintScanBroker = v16(v15, *v18, v17);
              WindowsDeleteString(*(HSTRING *)StringSecurityDescriptorLen);
              *(_QWORD *)StringSecurityDescriptorLen = 0;
              WindowsDeleteString(string);
              if ( PrintScanBroker < 0 )
                LocalSpoolerTelemetry::WriteDbgTraceError(
                  "BrokerPrinterShareOperation",
                  L"UnsharePrinter failed. Error 0x%x",
                  (unsigned int)PrintScanBroker);
            }
          }
          else
          {
            v19 = v37;
            v20 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64, __int64, __int64, __int64))(*(_QWORD *)v37 + 200LL);
            v21 = *(_QWORD *)HStringWrapper(v41, StringSecurityDescriptor);
            v22 = *(_QWORD *)HStringWrapper(&string, a5);
            v23 = *(_QWORD *)HStringWrapper(&v40, a4);
            v24 = *(_QWORD *)HStringWrapper(&v39, a3);
            v25 = (_QWORD *)HStringWrapper(StringSecurityDescriptorLen, a2);
            PrintScanBroker = v20(v19, *v25, v24, v23, v22, v21);
            WindowsDeleteString(*(HSTRING *)StringSecurityDescriptorLen);
            *(_QWORD *)StringSecurityDescriptorLen = 0;
            WindowsDeleteString(v39);
            v39 = 0;
            WindowsDeleteString(v40);
            v40 = 0;
            WindowsDeleteString(string);
            string = 0;
            WindowsDeleteString(v41[0]);
            if ( PrintScanBroker < 0 )
              LocalSpoolerTelemetry::WriteDbgTraceError(
                "BrokerPrinterShareOperation",
                L"UpdatePrinterShare failed. Error 0x%x",
                (unsigned int)PrintScanBroker);
          }
        }
        else
        {
          v26 = v37;
          v27 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64, __int64, __int64, __int64))(*(_QWORD *)v37 + 192LL);
          v28 = *(_QWORD *)HStringWrapper(v41, StringSecurityDescriptor);
          v29 = *(_QWORD *)HStringWrapper(StringSecurityDescriptorLen, a5);
          v30 = *(_QWORD *)HStringWrapper(&v39, a4);
          v31 = *(_QWORD *)HStringWrapper(&v40, a3);
          v32 = (_QWORD *)HStringWrapper(&string, a2);
          PrintScanBroker = v27(v26, *v32, v31, v30, v29, v28);
          WindowsDeleteString(string);
          string = 0;
          WindowsDeleteString(v40);
          v40 = 0;
          WindowsDeleteString(v39);
          v39 = 0;
          WindowsDeleteString(*(HSTRING *)StringSecurityDescriptorLen);
          *(_QWORD *)StringSecurityDescriptorLen = 0;
          WindowsDeleteString(v41[0]);
          if ( PrintScanBroker < 0 )
            LocalSpoolerTelemetry::WriteDbgTraceError(
              "BrokerPrinterShareOperation",
              L"SharePrinter failed. Error 0x%x",
              (unsigned int)PrintScanBroker);
        }
      }
      else
      {
        LastError = GetLastError();
        PrintScanBroker = LastError;
        if ( LastError > 0 )
          PrintScanBroker = (unsigned __int16)LastError | 0x80070000;
        LocalSpoolerTelemetry::WriteDbgTraceError(
          "BrokerPrinterShareOperation",
          L"ConvertSecurityDescriptorToStringSecurityDescriptor failed. Error 0x%x",
          (unsigned int)PrintScanBroker);
      }
    }
    else
    {
      LocalSpoolerTelemetry::WriteDbgTraceError(
        "BrokerPrinterShareOperation",
        L"GetPrintScanBroker failed. Error 0x%x",
        (unsigned int)PrintScanBroker);
    }
    wil::com_ptr_t<Windows::Graphics::Internal::Printing::PrintScanBroker::IPrintScanBrokerHandler,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Internal::Printing::PrintScanBroker::IPrintScanBrokerHandler,wil::err_returncode_policy>(&v37);
    if ( StringSecurityDescriptor )
      LocalFree(StringSecurityDescriptor);
    if ( v34 )
      CoUninitialize();
  }
  else
  {
    LocalSpoolerTelemetry::WriteDbgTraceError(
      "BrokerPrinterShareOperation",
      L"CoInitializeEx failed. Error 0x%x",
      (unsigned int)PrintScanBroker);
  }
  return (unsigned int)PrintScanBroker;
}

```

## disassembly

```asm
0x1800c7370  mov     rax, rsp
0x1800c7373  mov     [rax+8], rbx
0x1800c7377  mov     [rax+20h], r9
0x1800c737b  mov     [rax+18h], r8
0x1800c737f  push    rbp
0x1800c7380  push    rsi
0x1800c7381  push    rdi
0x1800c7382  push    r12
0x1800c7384  push    r13
0x1800c7386  push    r14
0x1800c7388  push    r15
0x1800c738a  lea     rbp, [rax-4Fh]
0x1800c738e  sub     rsp, 0A0h
0x1800c7395  mov     r13, rdx
0x1800c7398  mov     edi, ecx
0x1800c739a  xor     edx, edx; dwCoInit
0x1800c739c  xor     ecx, ecx; pvReserved
0x1800c739e  call    cs:__imp_CoInitializeEx
0x1800c73a4  mov     ebx, eax
0x1800c73a6  mov     ecx, 80000000h
0x1800c73ab  add     eax, ecx
0x1800c73ad  test    ecx, eax
0x1800c73af  jnz     short loc_1800C73D4
0x1800c73b1  cmp     ebx, 80010106h
0x1800c73b7  jz      short loc_1800C73D4
0x1800c73b9  mov     r8d, ebx
0x1800c73bc  lea     rdx, aCoinitializeex_0; "CoInitializeEx failed. Error 0x%x"
0x1800c73c3  lea     rcx, aBrokerprinters_0; "BrokerPrinterShareOperation"
0x1800c73ca  call    ?WriteDbgTraceError@LocalSpoolerTelemetry@@SAXPEADPEAGZZ; LocalSpoolerTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x1800c73cf  jmp     loc_1800C7724
0x1800c73d4  shr     ebx, 1Fh
0x1800c73d7  xor     bl, 1
0x1800c73da  mov     [rbp+47h+var_90], bl
0x1800c73dd  xor     r14d, r14d
0x1800c73e0  mov     [rbp+47h+StringSecurityDescriptor], r14
0x1800c73e4  lea     rax, [rbp+47h+StringSecurityDescriptor]
0x1800c73e8  mov     [rbp+47h+var_50], rax
0x1800c73ec  lea     rax, [rbp+47h+var_90]
0x1800c73f0  mov     [rbp+47h+var_48], rax
0x1800c73f4  mov     [rbp+47h+var_40], 1
0x1800c73f8  mov     [rbp+47h+var_78], r14
0x1800c73fc  lea     rcx, [rbp+47h+var_78]
0x1800c7400  call    ?GetPrintScanBroker@@YAJAEAV?$com_ptr_t@UIPrintScanBrokerHandler@PrintScanBroker@Printing@Internal@Graphics@Windows@@Uerr_returncode_policy@wil@@@wil@@@Z; GetPrintScanBroker(wil::com_ptr_t<Windows::Graphics::Internal::Printing::PrintScanBroker::IPrintScanBrokerHandler,wil::err_returncode_policy> &)
0x1800c7405  mov     ebx, eax
0x1800c7407  test    eax, eax
0x1800c7409  jns     short loc_1800C7417
0x1800c740b  lea     rdx, aGetprintscanbr; "GetPrintScanBroker failed. Error 0x%x"
0x1800c7412  jmp     loc_1800C76EF
0x1800c7417  mov     rcx, [rbp+47h+SecurityDescriptor]; SecurityDescriptor
0x1800c741b  test    rcx, rcx
0x1800c741e  jz      short loc_1800C7465
0x1800c7420  mov     [rbp+47h+var_88], r14d
0x1800c7424  lea     rax, [rbp+47h+var_88]
0x1800c7428  mov     [rsp+0D0h+StringSecurityDescriptorLen], rax; StringSecurityDescriptorLen
0x1800c742d  lea     r9, [rbp+47h+StringSecurityDescriptor]; StringSecurityDescriptor
0x1800c7431  mov     edx, 1; RequestedStringSDRevision
0x1800c7436  lea     r8d, [rdx+6]; SecurityInformation
0x1800c743a  call    cs:__imp_ConvertSecurityDescriptorToStringSecurityDescriptorW
0x1800c7440  test    eax, eax
0x1800c7442  jnz     short loc_1800C7465
0x1800c7444  call    cs:__imp_GetLastError
0x1800c744a  mov     ebx, eax
0x1800c744c  test    eax, eax
0x1800c744e  jle     short loc_1800C7459
0x1800c7450  movzx   ebx, ax
0x1800c7453  or      ebx, 80070000h
0x1800c7459  lea     rdx, aConvertsecurit_0; "ConvertSecurityDescriptorToStringSecuri"...
0x1800c7460  jmp     loc_1800C76EF
0x1800c7465  test    edi, edi
0x1800c7467  jz      loc_1800C761F
0x1800c746d  sub     edi, 1
0x1800c7470  jz      loc_1800C7546
0x1800c7476  sub     edi, 1
0x1800c7479  jz      short loc_1800C74DB
0x1800c747b  cmp     edi, 1
0x1800c747e  jz      short loc_1800C7491
0x1800c7480  mov     ebx, 80070057h
0x1800c7485  lea     rdx, aInvalidSharing; "Invalid SharingOperation. Error 0x%x"
0x1800c748c  jmp     loc_1800C76EF
0x1800c7491  mov     rdi, [rbp+47h+var_78]
0x1800c7495  mov     rax, [rdi]
0x1800c7498  mov     rbx, [rax+0D8h]
0x1800c749f  mov     rdx, [rbp+47h+arg_20]
0x1800c74a3  lea     rcx, [rbp+47h+string]
0x1800c74a7  call    ?HStringWrapper@@YA?AVHString@Wrappers@WRL@Microsoft@@PEBG@Z; HStringWrapper(ushort const *)
0x1800c74ac  nop
0x1800c74ad  mov     rdx, [rax]
0x1800c74b0  mov     rcx, rdi
0x1800c74b3  mov     rax, rbx
0x1800c74b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c74bb  mov     ebx, eax
0x1800c74bd  mov     rcx, [rbp+47h+string]; string
0x1800c74c1  call    cs:__imp_WindowsDeleteString
0x1800c74c7  test    ebx, ebx
0x1800c74c9  jns     loc_1800C76FF
0x1800c74cf  lea     rdx, aUnshareallprin; "UnshareAllPrinters failed. Error 0x%x"
0x1800c74d6  jmp     loc_1800C76EF
0x1800c74db  mov     rsi, [rbp+47h+var_78]
0x1800c74df  mov     rax, [rsi]
0x1800c74e2  mov     rdi, [rax+0D0h]
0x1800c74e9  mov     rdx, [rbp+47h+arg_20]
0x1800c74ed  lea     rcx, [rbp+47h+string]
0x1800c74f1  call    ?HStringWrapper@@YA?AVHString@Wrappers@WRL@Microsoft@@PEBG@Z; HStringWrapper(ushort const *)
0x1800c74f6  nop
0x1800c74f7  mov     rbx, [rax]
0x1800c74fa  mov     rdx, r13
0x1800c74fd  lea     rcx, [rbp+47h+var_88]
0x1800c7501  call    ?HStringWrapper@@YA?AVHString@Wrappers@WRL@Microsoft@@PEBG@Z; HStringWrapper(ushort const *)
0x1800c7506  nop
0x1800c7507  mov     r8, rbx
0x1800c750a  mov     rdx, [rax]
0x1800c750d  mov     rcx, rsi
0x1800c7510  mov     rax, rdi
0x1800c7513  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c7518  mov     ebx, eax
0x1800c751a  mov     rcx, qword ptr [rbp+47h+var_88]; string
0x1800c751e  call    cs:__imp_WindowsDeleteString
0x1800c7524  mov     qword ptr [rbp+47h+var_88], r14
0x1800c7528  mov     rcx, [rbp+47h+string]; string
0x1800c752c  call    cs:__imp_WindowsDeleteString
0x1800c7532  test    ebx, ebx
0x1800c7534  jns     loc_1800C76FF
0x1800c753a  lea     rdx, aUnshareprinter; "UnsharePrinter failed. Error 0x%x"
0x1800c7541  jmp     loc_1800C76EF
0x1800c7546  mov     r12, [rbp+47h+var_78]
0x1800c754a  mov     rax, [r12]
0x1800c754e  mov     r15, [rax+0C8h]
0x1800c7555  mov     rdx, [rbp+47h+StringSecurityDescriptor]
0x1800c7559  lea     rcx, [rbp+47h+var_58]
0x1800c755d  call    ?HStringWrapper@@YA?AVHString@Wrappers@WRL@Microsoft@@PEBG@Z; HStringWrapper(ushort const *)
0x1800c7562  nop
0x1800c7563  mov     r14, [rax]
0x1800c7566  mov     rdx, [rbp+47h+arg_20]
0x1800c756a  lea     rcx, [rbp+47h+string]
0x1800c756e  call    ?HStringWrapper@@YA?AVHString@Wrappers@WRL@Microsoft@@PEBG@Z; HStringWrapper(ushort const *)
0x1800c7573  nop
0x1800c7574  mov     rsi, [rax]
0x1800c7577  mov     rdx, [rbp+47h+arg_18]
0x1800c757b  lea     rcx, [rbp+47h+var_60]
0x1800c757f  call    ?HStringWrapper@@YA?AVHString@Wrappers@WRL@Microsoft@@PEBG@Z; HStringWrapper(ushort const *)
0x1800c7584  nop
0x1800c7585  mov     rdi, [rax]
0x1800c7588  mov     rdx, [rbp+47h+arg_10]
0x1800c758c  lea     rcx, [rbp+47h+var_68]
0x1800c7590  call    ?HStringWrapper@@YA?AVHString@Wrappers@WRL@Microsoft@@PEBG@Z; HStringWrapper(ushort const *)
0x1800c7595  nop
0x1800c7596  mov     rbx, [rax]
0x1800c7599  mov     rdx, r13
0x1800c759c  lea     rcx, [rbp+47h+var_88]
0x1800c75a0  call    ?HStringWrapper@@YA?AVHString@Wrappers@WRL@Microsoft@@PEBG@Z; HStringWrapper(ushort const *)
0x1800c75a5  nop
0x1800c75a6  mov     [rsp+28h], r14
0x1800c75ab  mov     [rsp+0D0h+StringSecurityDescriptorLen], rsi
0x1800c75b0  mov     r9, rdi
0x1800c75b3  mov     r8, rbx
0x1800c75b6  mov     rdx, [rax]
0x1800c75b9  mov     rcx, r12
0x1800c75bc  mov     rax, r15
0x1800c75bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c75c4  mov     ebx, eax
0x1800c75c6  mov     rcx, qword ptr [rbp+47h+var_88]; string
0x1800c75ca  call    cs:__imp_WindowsDeleteString
0x1800c75d0  xor     r14d, r14d
0x1800c75d3  mov     qword ptr [rbp+47h+var_88], r14
0x1800c75d7  mov     rcx, [rbp+47h+var_68]; string
0x1800c75db  call    cs:__imp_WindowsDeleteString
0x1800c75e1  mov     [rbp+47h+var_68], r14
0x1800c75e5  mov     rcx, [rbp+47h+var_60]; string
0x1800c75e9  call    cs:__imp_WindowsDeleteString
0x1800c75ef  mov     [rbp+47h+var_60], r14
0x1800c75f3  mov     rcx, [rbp+47h+string]; string
0x1800c75f7  call    cs:__imp_WindowsDeleteString
0x1800c75fd  mov     [rbp+47h+string], r14
0x1800c7601  mov     rcx, [rbp+47h+var_58]; string
0x1800c7605  call    cs:__imp_WindowsDeleteString
0x1800c760b  test    ebx, ebx
0x1800c760d  jns     loc_1800C76FF
0x1800c7613  lea     rdx, aUpdateprinters; "UpdatePrinterShare failed. Error 0x%x"
0x1800c761a  jmp     loc_1800C76EF
0x1800c761f  mov     r12, [rbp+47h+var_78]
0x1800c7623  mov     rax, [r12]
0x1800c7627  mov     r15, [rax+0C0h]
0x1800c762e  mov     rdx, [rbp+47h+StringSecurityDescriptor]
0x1800c7632  lea     rcx, [rbp+47h+var_58]
0x1800c7636  call    ?HStringWrapper@@YA?AVHString@Wrappers@WRL@Microsoft@@PEBG@Z; HStringWrapper(ushort const *)
0x1800c763b  nop
0x1800c763c  mov     r14, [rax]
0x1800c763f  mov     rdx, [rbp+47h+arg_20]
0x1800c7643  lea     rcx, [rbp+47h+var_88]
0x1800c7647  call    ?HStringWrapper@@YA?AVHString@Wrappers@WRL@Microsoft@@PEBG@Z; HStringWrapper(ushort const *)
0x1800c764c  nop
0x1800c764d  mov     rsi, [rax]
0x1800c7650  mov     rdx, [rbp+47h+arg_18]
0x1800c7654  lea     rcx, [rbp+47h+var_68]
0x1800c7658  call    ?HStringWrapper@@YA?AVHString@Wrappers@WRL@Microsoft@@PEBG@Z; HStringWrapper(ushort const *)
0x1800c765d  nop
0x1800c765e  mov     rdi, [rax]
0x1800c7661  mov     rdx, [rbp+47h+arg_10]
0x1800c7665  lea     rcx, [rbp+47h+var_60]
0x1800c7669  call    ?HStringWrapper@@YA?AVHString@Wrappers@WRL@Microsoft@@PEBG@Z; HStringWrapper(ushort const *)
0x1800c766e  nop
0x1800c766f  mov     rbx, [rax]
0x1800c7672  mov     rdx, r13
0x1800c7675  lea     rcx, [rbp+47h+string]
0x1800c7679  call    ?HStringWrapper@@YA?AVHString@Wrappers@WRL@Microsoft@@PEBG@Z; HStringWrapper(ushort const *)
0x1800c767e  nop
0x1800c767f  mov     [rsp+28h], r14
0x1800c7684  mov     [rsp+0D0h+StringSecurityDescriptorLen], rsi
0x1800c7689  mov     r9, rdi
0x1800c768c  mov     r8, rbx
0x1800c768f  mov     rdx, [rax]
0x1800c7692  mov     rcx, r12
0x1800c7695  mov     rax, r15
0x1800c7698  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c769d  mov     ebx, eax
0x1800c769f  mov     rcx, [rbp+47h+string]; string
0x1800c76a3  call    cs:__imp_WindowsDeleteString
0x1800c76a9  xor     r14d, r14d
0x1800c76ac  mov     [rbp+47h+string], r14
0x1800c76b0  mov     rcx, [rbp+47h+var_60]; string
0x1800c76b4  call    cs:__imp_WindowsDeleteString
0x1800c76ba  mov     [rbp+47h+var_60], r14
0x1800c76be  mov     rcx, [rbp+47h+var_68]; string
0x1800c76c2  call    cs:__imp_WindowsDeleteString
0x1800c76c8  mov     [rbp+47h+var_68], r14
0x1800c76cc  mov     rcx, qword ptr [rbp+47h+var_88]; string
0x1800c76d0  call    cs:__imp_WindowsDeleteString
0x1800c76d6  mov     qword ptr [rbp+47h+var_88], r14
0x1800c76da  mov     rcx, [rbp+47h+var_58]; string
0x1800c76de  call    cs:__imp_WindowsDeleteString
0x1800c76e4  test    ebx, ebx
0x1800c76e6  jns     short loc_1800C76FF
0x1800c76e8  lea     rdx, aShareprinterFa; "SharePrinter failed. Error 0x%x"
0x1800c76ef  mov     r8d, ebx
0x1800c76f2  lea     rcx, aBrokerprinters_0; "BrokerPrinterShareOperation"
0x1800c76f9  call    ?WriteDbgTraceError@LocalSpoolerTelemetry@@SAXPEADPEAGZZ; LocalSpoolerTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x1800c76fe  nop
0x1800c76ff  lea     rcx, [rbp+47h+var_78]
0x1800c7703  call    ??1?$com_ptr_t@UIPrintScanBrokerHandler@PrintScanBroker@Printing@Internal@Graphics@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Graphics::Internal::Printing::PrintScanBroker::IPrintScanBrokerHandler,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Internal::Printing::PrintScanBroker::IPrintScanBrokerHandler,wil::err_returncode_policy>(void)
0x1800c7708  nop
0x1800c7709  mov     rcx, [rbp+47h+StringSecurityDescriptor]; hMem
0x1800c770d  test    rcx, rcx
0x1800c7710  jz      short loc_1800C7718
0x1800c7712  call    cs:__imp_LocalFree
0x1800c7718  cmp     [rbp+47h+var_90], r14b
0x1800c771c  jz      short loc_1800C7724
0x1800c771e  call    cs:__imp_CoUninitialize
0x1800c7724  mov     eax, ebx
0x1800c7726  mov     rbx, [rsp+0D0h+arg_0]
0x1800c772e  add     rsp, 0A0h
0x1800c7735  pop     r15
0x1800c7737  pop     r14
0x1800c7739  pop     r13
0x1800c773b  pop     r12
0x1800c773d  pop     rdi
0x1800c773e  pop     rsi
0x1800c773f  pop     rbp
0x1800c7740  retn
```
