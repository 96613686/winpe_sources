# GetActiveSessionSidViaBroker(void * *)

- ea: `0x1800c7748`
- end: `0x1800c7916`
- name: `?GetActiveSessionSidViaBroker@@YAJPEAPEAX@Z`
- size: `462`
- prototype: `__int64 __fastcall(void **)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800982c8`

## callees

- `0x18003ea2c`
- `0x18005c718`
- `0x1800c72e4`
- `0x1800c7748`
- `0x1800c7c1c`
- `0x1800e6010`

## import_xrefs

- `ntdll!RtlCopySid` at `0x1800c783e`
- `ntdll!RtlCopySid` at `0x1800c783e`
- `ntdll!RtlLengthSid` at `0x1800c781d`
- `ntdll!RtlLengthSid` at `0x1800c781d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c7886`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c7886`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800c7802`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800c7802`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c77cd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c78d7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c77cd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c78d7`
- `SPOOLSS!DllFreeSplMem` at `0x1800c7870`
- `SPOOLSS!DllFreeSplMem` at `0x1800c7870`
- `SPOOLSS!DllAllocSplMem` at `0x1800c7827`
- `SPOOLSS!DllAllocSplMem` at `0x1800c7827`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x1800c7764`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x1800c7764`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1800c78f9`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1800c78f9`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x1800c780f`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x1800c780f`

## string_xrefs

- `0x1800c785a`: `RtlCopySid failed. Error 0x%x`
- `0x1800c778c`: `GetActiveSessionSidViaBroker`
- `0x1800c7861`: `GetActiveSessionSidViaBroker`
- `0x1800c78a5`: `GetActiveSessionSidViaBroker`
- `0x1800c78c6`: `GetActiveSessionSidViaBroker`
- `0x1800c78e9`: `GetActiveSessionSidViaBroker`
- `0x1800c789e`: `ConvertStringSidToSid failed. Error 0x%x`
- `0x1800c78bf`: `GetUserSidForActiveSession failed. Error 0x%x`
- `0x1800c78e2`: `GetPrintScanBroker failed. Error 0x%x`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall GetActiveSessionSidViaBroker(void **a1)
{
  HRESULT v2; // esi
  unsigned int v3; // ebx
  int PrintScanBroker; // eax
  __int64 v5; // rdi
  __int64 (__fastcall *v6)(__int64, HSTRING *); // rbx
  int v7; // eax
  const WCHAR *StringRawBuffer; // rax
  ULONG v9; // ebx
  void *v10; // rax
  NTSTATUS v11; // eax
  signed int LastError; // eax
  PSID Sid; // [rsp+50h] [rbp+30h] BYREF
  HSTRING string; // [rsp+58h] [rbp+38h] BYREF
  __int64 v16; // [rsp+60h] [rbp+40h] BYREF

  *a1 = 0;
  v2 = CoInitializeEx(0, 0);
  if ( (int)(v2 + 0x80000000) < 0 || v2 == -2147417850 )
  {
    v16 = 0;
    PrintScanBroker = GetPrintScanBroker(&v16);
    v3 = PrintScanBroker;
    if ( PrintScanBroker < 0 )
    {
      LocalSpoolerTelemetry::WriteDbgTraceError(
        "GetActiveSessionSidViaBroker",
        L"GetPrintScanBroker failed. Error 0x%x",
        (unsigned int)PrintScanBroker);
    }
    else
    {
      string = 0;
      v5 = v16;
      v6 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v16 + 104LL);
      WindowsDeleteString(0);
      string = 0;
      v7 = v6(v5, &string);
      v3 = v7;
      if ( v7 < 0 )
      {
        LocalSpoolerTelemetry::WriteDbgTraceError(
          "GetActiveSessionSidViaBroker",
          L"GetUserSidForActiveSession failed. Error 0x%x",
          (unsigned int)v7);
      }
      else
      {
        Sid = 0;
        StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
        if ( ConvertStringSidToSidW(StringRawBuffer, &Sid) )
        {
          v9 = RtlLengthSid(Sid);
          v10 = (void *)DllAllocSplMem(v9);
          *a1 = v10;
          if ( v10 )
          {
            v11 = RtlCopySid(v9, v10, Sid);
            v3 = v11;
            if ( v11 > 0 )
              v3 = (unsigned __int16)v11 | 0x80070000;
            if ( (v3 & 0x80000000) != 0 )
            {
              LocalSpoolerTelemetry::WriteDbgTraceError(
                "GetActiveSessionSidViaBroker",
                L"RtlCopySid failed. Error 0x%x",
                v3);
              DllFreeSplMem(*a1);
              *a1 = 0;
            }
          }
          else
          {
            v3 = -2147024882;
          }
        }
        else
        {
          LastError = GetLastError();
          v3 = LastError;
          if ( LastError > 0 )
            v3 = (unsigned __int16)LastError | 0x80070000;
          LocalSpoolerTelemetry::WriteDbgTraceError(
            "GetActiveSessionSidViaBroker",
            L"ConvertStringSidToSid failed. Error 0x%x",
            v3);
        }
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&Sid);
      }
      WindowsDeleteString(string);
    }
    if ( v2 >= 0 )
      CoUninitialize();
    wil::com_ptr_t<Windows::Graphics::Internal::Printing::PrintScanBroker::IPrintScanBrokerHandler,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Internal::Printing::PrintScanBroker::IPrintScanBrokerHandler,wil::err_returncode_policy>(&v16);
  }
  else
  {
    v3 = v2;
    LocalSpoolerTelemetry::WriteDbgTraceError(
      "GetActiveSessionSidViaBroker",
      L"CoInitializeEx failed. Error 0x%x",
      (unsigned int)v2);
  }
  return v3;
}

```

## disassembly

```asm
0x1800c7748  push    rbp
0x1800c774a  push    rbx
0x1800c774b  push    rsi
0x1800c774c  push    rdi
0x1800c774d  push    r14
0x1800c774f  mov     rbp, rsp
0x1800c7752  sub     rsp, 20h
0x1800c7756  mov     r14, rcx
0x1800c7759  mov     qword ptr [rcx], 0
0x1800c7760  xor     edx, edx; dwCoInit
0x1800c7762  xor     ecx, ecx; pvReserved
0x1800c7764  call    cs:__imp_CoInitializeEx
0x1800c776a  mov     esi, eax
0x1800c776c  mov     eax, 80000000h
0x1800c7771  lea     edx, [rsi+rax]
0x1800c7774  test    eax, edx
0x1800c7776  jnz     short loc_1800C779D
0x1800c7778  cmp     esi, 80010106h
0x1800c777e  jz      short loc_1800C779D
0x1800c7780  mov     ebx, esi
0x1800c7782  mov     r8d, esi
0x1800c7785  lea     rdx, aCoinitializeex_0; "CoInitializeEx failed. Error 0x%x"
0x1800c778c  lea     rcx, aGetactivesessi; "GetActiveSessionSidViaBroker"
0x1800c7793  call    ?WriteDbgTraceError@LocalSpoolerTelemetry@@SAXPEADPEAGZZ; LocalSpoolerTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x1800c7798  jmp     loc_1800C7909
0x1800c779d  mov     [rbp+arg_10], 0
0x1800c77a5  lea     rcx, [rbp+arg_10]
0x1800c77a9  call    ?GetPrintScanBroker@@YAJAEAV?$com_ptr_t@UIPrintScanBrokerHandler@PrintScanBroker@Printing@Internal@Graphics@Windows@@Uerr_returncode_policy@wil@@@wil@@@Z; GetPrintScanBroker(wil::com_ptr_t<Windows::Graphics::Internal::Printing::PrintScanBroker::IPrintScanBrokerHandler,wil::err_returncode_policy> &)
0x1800c77ae  mov     ebx, eax
0x1800c77b0  test    eax, eax
0x1800c77b2  js      loc_1800C78DF
0x1800c77b8  mov     [rbp+string], 0
0x1800c77c0  mov     rdi, [rbp+arg_10]
0x1800c77c4  mov     rax, [rdi]
0x1800c77c7  mov     rbx, [rax+68h]
0x1800c77cb  xor     ecx, ecx; string
0x1800c77cd  call    cs:__imp_WindowsDeleteString
0x1800c77d3  mov     [rbp+string], 0
0x1800c77db  lea     rdx, [rbp+string]
0x1800c77df  mov     rcx, rdi
0x1800c77e2  mov     rax, rbx
0x1800c77e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c77ea  mov     ebx, eax
0x1800c77ec  test    eax, eax
0x1800c77ee  js      loc_1800C78BC
0x1800c77f4  mov     [rbp+Sid], 0
0x1800c77fc  xor     edx, edx; length
0x1800c77fe  mov     rcx, [rbp+string]; string
0x1800c7802  call    cs:__imp_WindowsGetStringRawBuffer
0x1800c7808  lea     rdx, [rbp+Sid]; Sid
0x1800c780c  mov     rcx, rax; StringSid
0x1800c780f  call    cs:__imp_ConvertStringSidToSidW
0x1800c7815  test    eax, eax
0x1800c7817  jz      short loc_1800C7886
0x1800c7819  mov     rcx, [rbp+Sid]; Sid
0x1800c781d  call    cs:__imp_RtlLengthSid
0x1800c7823  mov     ebx, eax
0x1800c7825  mov     ecx, eax
0x1800c7827  call    cs:__imp_DllAllocSplMem
0x1800c782d  mov     [r14], rax
0x1800c7830  test    rax, rax
0x1800c7833  jz      short loc_1800C787F
0x1800c7835  mov     r8, [rbp+Sid]; SourceSid
0x1800c7839  mov     rdx, rax; DestinationSid
0x1800c783c  mov     ecx, ebx; DestinationSidLength
0x1800c783e  call    cs:__imp_RtlCopySid
0x1800c7844  mov     ebx, eax
0x1800c7846  test    eax, eax
0x1800c7848  jle     short loc_1800C7853
0x1800c784a  movzx   ebx, ax
0x1800c784d  or      ebx, 80070000h
0x1800c7853  test    ebx, ebx
0x1800c7855  jns     short loc_1800C78B1
0x1800c7857  mov     r8d, ebx
0x1800c785a  lea     rdx, aRtlcopysidFail; "RtlCopySid failed. Error 0x%x"
0x1800c7861  lea     rcx, aGetactivesessi; "GetActiveSessionSidViaBroker"
0x1800c7868  call    ?WriteDbgTraceError@LocalSpoolerTelemetry@@SAXPEADPEAGZZ; LocalSpoolerTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x1800c786d  mov     rcx, [r14]
0x1800c7870  call    cs:__imp_DllFreeSplMem
0x1800c7876  mov     qword ptr [r14], 0
0x1800c787d  jmp     short loc_1800C78B1
0x1800c787f  mov     ebx, 8007000Eh
0x1800c7884  jmp     short loc_1800C78B1
0x1800c7886  call    cs:__imp_GetLastError
0x1800c788c  mov     ebx, eax
0x1800c788e  test    eax, eax
0x1800c7890  jle     short loc_1800C789B
0x1800c7892  movzx   ebx, ax
0x1800c7895  or      ebx, 80070000h
0x1800c789b  mov     r8d, ebx
0x1800c789e  lea     rdx, aConvertstrings_1; "ConvertStringSidToSid failed. Error 0x%"...
0x1800c78a5  lea     rcx, aGetactivesessi; "GetActiveSessionSidViaBroker"
0x1800c78ac  call    ?WriteDbgTraceError@LocalSpoolerTelemetry@@SAXPEADPEAGZZ; LocalSpoolerTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x1800c78b1  lea     rcx, [rbp+Sid]
0x1800c78b5  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800c78ba  jmp     short loc_1800C78D3
0x1800c78bc  mov     r8d, eax
0x1800c78bf  lea     rdx, aGetusersidfora; "GetUserSidForActiveSession failed. Erro"...
0x1800c78c6  lea     rcx, aGetactivesessi; "GetActiveSessionSidViaBroker"
0x1800c78cd  call    ?WriteDbgTraceError@LocalSpoolerTelemetry@@SAXPEADPEAGZZ; LocalSpoolerTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x1800c78d2  nop
0x1800c78d3  mov     rcx, [rbp+string]; string
0x1800c78d7  call    cs:__imp_WindowsDeleteString
0x1800c78dd  jmp     short loc_1800C78F5
0x1800c78df  mov     r8d, eax
0x1800c78e2  lea     rdx, aGetprintscanbr; "GetPrintScanBroker failed. Error 0x%x"
0x1800c78e9  lea     rcx, aGetactivesessi; "GetActiveSessionSidViaBroker"
0x1800c78f0  call    ?WriteDbgTraceError@LocalSpoolerTelemetry@@SAXPEADPEAGZZ; LocalSpoolerTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x1800c78f5  test    esi, esi
0x1800c78f7  js      short loc_1800C7900
0x1800c78f9  call    cs:__imp_CoUninitialize
0x1800c78ff  nop
0x1800c7900  lea     rcx, [rbp+arg_10]
0x1800c7904  call    ??1?$com_ptr_t@UIPrintScanBrokerHandler@PrintScanBroker@Printing@Internal@Graphics@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Graphics::Internal::Printing::PrintScanBroker::IPrintScanBrokerHandler,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Internal::Printing::PrintScanBroker::IPrintScanBrokerHandler,wil::err_returncode_policy>(void)
0x1800c7909  mov     eax, ebx
0x1800c790b  add     rsp, 20h
0x1800c790f  pop     r14
0x1800c7911  pop     rdi
0x1800c7912  pop     rsi
0x1800c7913  pop     rbx
0x1800c7914  pop     rbp
0x1800c7915  retn
```
