# CreateDiagnosticReportFromStreams(std::vector<IStream *,std::allocator<IStream *>>,ushort const *)

- ea: `0x180125c24`
- end: `0x180126053`
- name: `?CreateDiagnosticReportFromStreams@@YAJV?$vector@PEAUIStream@@V?$allocator@PEAUIStream@@@std@@@std@@PEBG@Z`
- size: `1071`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800fad60`

## callees

- `0x1800ead14`
- `0x1800ece5c`
- `0x1800ef3c4`
- `0x1800f7f10`
- `0x18010450c`
- `0x180125c24`
- `0x18012605c`
- `0x1801261b8`
- `0x18012628c`
- `0x180126364`
- `0x180191010`

## import_xrefs

- `api-ms-win-shcore-stream-l1-1-0!SHCreateStreamOnFileW` at `0x180125c88`
- `api-ms-win-shcore-stream-l1-1-0!SHCreateStreamOnFileW` at `0x180125c88`

## string_xrefs

- `0x180125c9c`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\reportfromstreams\registrydiagnosticreportfromstream.cpp`
- `0x180125d9d`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\reportfromstreams\registrydiagnosticreportfromstream.cpp`
- `0x180125ea1`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\reportfromstreams\registrydiagnosticreportfromstream.cpp`
- `0x180125f17`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\reportfromstreams\registrydiagnosticreportfromstream.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=5 #try_helpers=1
__int64 __fastcall CreateDiagnosticReportFromStreams(__int64 *a1, const unsigned __int16 *a2)
{
  signed int v4; // eax
  __int64 v5; // rcx
  unsigned int v6; // ebx
  HRESULT v7; // eax
  int v8; // eax
  __int64 v9; // rdx
  unsigned __int64 i; // rsi
  __int64 v12; // rdx
  struct IStream *v13; // rbx
  int v14; // eax
  unsigned int v15; // ebx
  int Report; // eax
  unsigned int v17; // ebx
  int v18; // [rsp+20h] [rbp-48h]
  IStream *ppstm; // [rsp+30h] [rbp-38h] BYREF
  struct IStream *v20[6]; // [rsp+38h] [rbp-30h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]
  struct IXmlReader *v22; // [rsp+80h] [rbp+18h] BYREF
  struct IXmlWriter *v23; // [rsp+88h] [rbp+20h] BYREF

  ppstm = 0;
  v4 = EnsureDirectoriesArePresent(a2);
  v6 = v4;
  if ( v4 < 0 )
  {
    if ( (Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits & 8) != 0 )
      McTemplateU0zd_EventWriteTransfer(
        v5,
        EnterpriseDiagnosticsMdmDiagnosticsCreatingOrCheckingDirectoryFailure,
        a2,
        (unsigned int)v4);
    goto LABEL_17;
  }
  Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&ppstm);
  v7 = SHCreateStreamOnFileW(a2, 0x1001u, &ppstm);
  v6 = v7;
  if ( v7 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xB0,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmdiagnostics\\reportfromstreams\\registrydiagnosticreportfromstream.cpp",
      (const char *)(unsigned int)v7,
      v18);
LABEL_17:
    Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&ppstm);
    std::vector<void *>::_Tidy(a1);
    return v6;
  }
  v23 = 0;
  Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&v23);
  v8 = InitializeReportGeneration(ppstm, &v23);
  v6 = v8;
  if ( v8 < 0 )
  {
    v9 = 179;
LABEL_16:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v9,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmdiagnostics\\reportfromstreams\\registrydiagnosticreportfromstream.cpp",
      (const char *)(unsigned int)v8,
      v18);
    Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&v23);
    goto LABEL_17;
  }
  v8 = ((__int64 (__fastcall *)(struct IXmlWriter *, _QWORD, const wchar_t *, _QWORD))v23->lpVtbl->WriteStartElement)(
         v23,
         0,
         L"MDMEnterpriseDiagnosticsReport",
         0);
  v6 = v8;
  if ( v8 < 0 )
  {
    v9 = 181;
    goto LABEL_16;
  }
  v8 = ((__int64 (__fastcall *)(struct IXmlWriter *, _QWORD, const wchar_t *, _QWORD))v23->lpVtbl->WriteStartElement)(
         v23,
         0,
         L"Version",
         0);
  v6 = v8;
  if ( v8 < 0 )
  {
    v9 = 182;
    goto LABEL_16;
  }
  v8 = ((__int64 (__fastcall *)(struct IXmlWriter *, const wchar_t *))v23->lpVtbl->WriteString)(v23, L"1.0");
  v6 = v8;
  if ( v8 < 0 )
  {
    v9 = 183;
    goto LABEL_16;
  }
  v8 = ((__int64 (__fastcall *)(struct IXmlWriter *))v23->lpVtbl->WriteFullEndElement)(v23);
  v6 = v8;
  if ( v8 < 0 )
  {
    v9 = 184;
    goto LABEL_16;
  }
  for ( i = 0; ; ++i )
  {
    v12 = *a1;
    if ( i >= (a1[1] - *a1) >> 3 )
      break;
    v20[0] = 0;
    Microsoft::WRL::ComPtr<IStream>::operator=(v20, *(_QWORD *)(v12 + 8 * i));
    v13 = v20[0];
    if ( !v20[0] )
    {
      Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(v20);
      Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&v23);
      Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&ppstm);
      std::vector<void *>::_Tidy(a1);
      return 2147942487LL;
    }
    v22 = 0;
    v20[1] = 0;
    (*(void (__fastcall **)(struct IStream *, _QWORD, _QWORD, _QWORD))(*(_QWORD *)v20[0] + 40LL))(v20[0], 0, 0, 0);
    Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&v22);
    v14 = InitializeDataGathering(v13, &v22);
    v15 = v14;
    if ( v14 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xCB,
        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmdiagnostics\\reportfromstreams\\registrydiagnosticreportfromstream.cpp",
        (const char *)(unsigned int)v14,
        v18);
      Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&v22);
      Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(v20);
      Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&v23);
      Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&ppstm);
      std::vector<void *>::_Tidy(a1);
      return v15;
    }
    Report = GenerateReport(v22, v23);
    v17 = Report;
    if ( Report < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xCC,
        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmdiagnostics\\reportfromstreams\\registrydiagnosticreportfromstream.cpp",
        (const char *)(unsigned int)Report,
        v18);
      Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&v22);
      Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(v20);
      Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&v23);
      Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&ppstm);
      std::vector<void *>::_Tidy(a1);
      return v17;
    }
    Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&v22);
    Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(v20);
  }
  v8 = ((__int64 (__fastcall *)(struct IXmlWriter *))v23->lpVtbl->WriteFullEndElement)(v23);
  v6 = v8;
  if ( v8 < 0 )
  {
    v9 = 209;
    goto LABEL_16;
  }
  v8 = ((__int64 (__fastcall *)(struct IXmlWriter *))v23->lpVtbl->WriteEndDocument)(v23);
  v6 = v8;
  if ( v8 < 0 )
  {
    v9 = 210;
    goto LABEL_16;
  }
  v8 = ((__int64 (__fastcall *)(struct IXmlWriter *))v23->lpVtbl->Flush)(v23);
  v6 = v8;
  if ( v8 < 0 )
  {
    v9 = 211;
    goto LABEL_16;
  }
  Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&v23);
  Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&ppstm);
  std::vector<void *>::_Tidy(a1);
  return 0;
}

```

## disassembly

```asm
0x180125c24  mov     [rsp+arg_0], rcx
0x180125c29  push    rbx
0x180125c2a  push    rsi
0x180125c2b  push    rdi
0x180125c2c  sub     rsp, 50h
0x180125c30  mov     rsi, rdx
0x180125c33  mov     rdi, rcx
0x180125c36  mov     [rsp+68h+ppstm], 0
0x180125c3f  mov     rcx, rdx; unsigned __int16 *
0x180125c42  call    ?EnsureDirectoriesArePresent@@YAJPEBG@Z; EnsureDirectoriesArePresent(ushort const *)
0x180125c47  mov     ebx, eax
0x180125c49  test    eax, eax
0x180125c4b  jns     short loc_180125C71
0x180125c4d  test    cs:Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits, 8
0x180125c54  jz      loc_180125DBD
0x180125c5a  mov     r9d, eax
0x180125c5d  mov     r8, rsi
0x180125c60  lea     rdx, EnterpriseDiagnosticsMdmDiagnosticsCreatingOrCheckingDirectoryFailure
0x180125c67  call    McTemplateU0zd_EventWriteTransfer
0x180125c6c  jmp     loc_180125DBD
0x180125c71  lea     rcx, [rsp+68h+ppstm]
0x180125c76  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x180125c7b  lea     r8, [rsp+68h+ppstm]; ppstm
0x180125c80  mov     edx, 1001h; grfMode
0x180125c85  mov     rcx, rsi; pszFile
0x180125c88  call    cs:__imp_SHCreateStreamOnFileW
0x180125c8e  mov     ebx, eax
0x180125c90  test    eax, eax
0x180125c92  jns     short loc_180125CB2
0x180125c94  mov     rcx, [rsp+68h]; this
0x180125c99  mov     r9d, eax; char *
0x180125c9c  lea     r8, aOnecoreuapAdmi_8; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x180125ca3  mov     edx, 0B0h; void *
0x180125ca8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180125cad  jmp     loc_180125DBD
0x180125cb2  mov     [rsp+68h+arg_18], 0
0x180125cbe  lea     rcx, [rsp+68h+arg_18]
0x180125cc6  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x180125ccb  lea     rdx, [rsp+68h+arg_18]; struct IXmlWriter **
0x180125cd3  mov     rcx, [rsp+68h+ppstm]; struct IStream *
0x180125cd8  call    ?InitializeReportGeneration@@YAJPEAUIStream@@PEAPEAUIXmlWriter@@@Z; InitializeReportGeneration(IStream *,IXmlWriter * *)
0x180125cdd  mov     ebx, eax
0x180125cdf  test    eax, eax
0x180125ce1  jns     short loc_180125CED
0x180125ce3  mov     edx, 0B3h
0x180125ce8  jmp     loc_180125D9A
0x180125ced  mov     rcx, [rsp+68h+arg_18]
0x180125cf5  mov     rax, [rcx]
0x180125cf8  xor     r9d, r9d
0x180125cfb  lea     r8, aMdmenterprised; "MDMEnterpriseDiagnosticsReport"
0x180125d02  xor     edx, edx
0x180125d04  mov     rax, [rax+0D8h]
0x180125d0b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180125d10  mov     ebx, eax
0x180125d12  test    eax, eax
0x180125d14  jns     short loc_180125D1D
0x180125d16  mov     edx, 0B5h
0x180125d1b  jmp     short loc_180125D9A
0x180125d1d  mov     rcx, [rsp+68h+arg_18]
0x180125d25  mov     rax, [rcx]
0x180125d28  xor     r9d, r9d
0x180125d2b  lea     r8, aVersion; "Version"
0x180125d32  xor     edx, edx
0x180125d34  mov     rax, [rax+0D8h]
0x180125d3b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180125d40  mov     ebx, eax
0x180125d42  test    eax, eax
0x180125d44  jns     short loc_180125D4D
0x180125d46  mov     edx, 0B6h
0x180125d4b  jmp     short loc_180125D9A
0x180125d4d  mov     rcx, [rsp+68h+arg_18]
0x180125d55  mov     rax, [rcx]
0x180125d58  lea     rdx, a10_1; "1.0"
0x180125d5f  mov     rax, [rax+0E0h]
0x180125d66  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180125d6b  mov     ebx, eax
0x180125d6d  test    eax, eax
0x180125d6f  jns     short loc_180125D78
0x180125d71  mov     edx, 0B7h
0x180125d76  jmp     short loc_180125D9A
0x180125d78  mov     rcx, [rsp+68h+arg_18]
0x180125d80  mov     rax, [rcx]
0x180125d83  mov     rax, [rax+88h]
0x180125d8a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180125d8f  mov     ebx, eax
0x180125d91  test    eax, eax
0x180125d93  jns     short loc_180125DD7
0x180125d95  mov     edx, 0B8h; void *
0x180125d9a  mov     r9d, eax; char *
0x180125d9d  lea     r8, aOnecoreuapAdmi_8; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x180125da4  mov     rcx, [rsp+68h]; this
0x180125da9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180125dae  nop
0x180125daf  lea     rcx, [rsp+68h+arg_18]
0x180125db7  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x180125dbc  nop
0x180125dbd  lea     rcx, [rsp+68h+ppstm]
0x180125dc2  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x180125dc7  nop
0x180125dc8  mov     rcx, rdi
0x180125dcb  call    ?_Tidy@?$vector@PEAXV?$allocator@PEAX@std@@@std@@AEAAXXZ; std::vector<void *>::_Tidy(void)
0x180125dd0  mov     eax, ebx
0x180125dd2  jmp     loc_18012604B
0x180125dd7  xor     esi, esi
0x180125dd9  mov     rdx, [rdi]
0x180125ddc  mov     rax, [rdi+8]
0x180125de0  sub     rax, rdx
0x180125de3  sar     rax, 3
0x180125de7  cmp     rsi, rax
0x180125dea  jnb     loc_180125F8A
0x180125df0  mov     [rsp+68h+var_30], 0
0x180125df9  mov     rdx, [rdx+rsi*8]
0x180125dfd  lea     rcx, [rsp+68h+var_30]
0x180125e02  call    ??4?$ComPtr@UIStream@@@WRL@Microsoft@@QEAAAEAV012@PEAUIStream@@@Z; Microsoft::WRL::ComPtr<IStream>::operator=(IStream *)
0x180125e07  mov     rbx, [rsp+68h+var_30]
0x180125e0c  test    rbx, rbx
0x180125e0f  jnz     short loc_180125E47
0x180125e11  lea     rcx, [rsp+68h+var_30]
0x180125e16  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x180125e1b  nop
0x180125e1c  lea     rcx, [rsp+68h+arg_18]
0x180125e24  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x180125e29  nop
0x180125e2a  lea     rcx, [rsp+68h+ppstm]
0x180125e2f  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x180125e34  nop
0x180125e35  mov     rcx, rdi
0x180125e38  call    ?_Tidy@?$vector@PEAXV?$allocator@PEAX@std@@@std@@AEAAXXZ; std::vector<void *>::_Tidy(void)
0x180125e3d  mov     eax, 80070057h
0x180125e42  jmp     loc_18012604B
0x180125e47  mov     [rsp+68h+arg_10], 0
0x180125e53  mov     [rsp+68h+var_28], 0
0x180125e5c  mov     rax, [rbx]
0x180125e5f  xor     r9d, r9d
0x180125e62  xor     r8d, r8d
0x180125e65  mov     rdx, [rsp+68h+var_28]
0x180125e6a  mov     rcx, rbx
0x180125e6d  mov     rax, [rax+28h]
0x180125e71  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180125e76  lea     rcx, [rsp+68h+arg_10]
0x180125e7e  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x180125e83  lea     rdx, [rsp+68h+arg_10]; struct IXmlReader **
0x180125e8b  mov     rcx, rbx; struct IStream *
0x180125e8e  call    ?InitializeDataGathering@@YAJPEAUIStream@@PEAPEAUIXmlReader@@@Z; InitializeDataGathering(IStream *,IXmlReader * *)
0x180125e93  mov     ebx, eax
0x180125e95  test    eax, eax
0x180125e97  jns     short loc_180125EF4
0x180125e99  mov     rcx, [rsp+68h]; this
0x180125e9e  mov     r9d, eax; char *
0x180125ea1  lea     r8, aOnecoreuapAdmi_8; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x180125ea8  mov     edx, 0CBh; void *
0x180125ead  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180125eb2  nop
0x180125eb3  lea     rcx, [rsp+68h+arg_10]
0x180125ebb  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x180125ec0  nop
0x180125ec1  lea     rcx, [rsp+68h+var_30]
0x180125ec6  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x180125ecb  nop
0x180125ecc  lea     rcx, [rsp+68h+arg_18]
0x180125ed4  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x180125ed9  nop
0x180125eda  lea     rcx, [rsp+68h+ppstm]
0x180125edf  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x180125ee4  nop
0x180125ee5  mov     rcx, rdi
0x180125ee8  call    ?_Tidy@?$vector@PEAXV?$allocator@PEAX@std@@@std@@AEAAXXZ; std::vector<void *>::_Tidy(void)
0x180125eed  mov     eax, ebx
0x180125eef  jmp     loc_18012604B
0x180125ef4  mov     rdx, [rsp+68h+arg_18]; struct IXmlWriter *
0x180125efc  mov     rcx, [rsp+68h+arg_10]; struct IXmlReader *
0x180125f04  call    ?GenerateReport@@YAJPEAUIXmlReader@@PEAUIXmlWriter@@@Z; GenerateReport(IXmlReader *,IXmlWriter *)
0x180125f09  mov     ebx, eax
0x180125f0b  test    eax, eax
0x180125f0d  jns     short loc_180125F6A
0x180125f0f  mov     rcx, [rsp+68h]; this
0x180125f14  mov     r9d, eax; char *
0x180125f17  lea     r8, aOnecoreuapAdmi_8; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x180125f1e  mov     edx, 0CCh; void *
0x180125f23  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180125f28  nop
0x180125f29  lea     rcx, [rsp+68h+arg_10]
0x180125f31  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x180125f36  nop
0x180125f37  lea     rcx, [rsp+68h+var_30]
0x180125f3c  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x180125f41  nop
0x180125f42  lea     rcx, [rsp+68h+arg_18]
0x180125f4a  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x180125f4f  nop
0x180125f50  lea     rcx, [rsp+68h+ppstm]
0x180125f55  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x180125f5a  nop
0x180125f5b  mov     rcx, rdi
0x180125f5e  call    ?_Tidy@?$vector@PEAXV?$allocator@PEAX@std@@@std@@AEAAXXZ; std::vector<void *>::_Tidy(void)
0x180125f63  mov     eax, ebx
0x180125f65  jmp     loc_18012604B
0x180125f6a  lea     rcx, [rsp+68h+arg_10]
0x180125f72  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x180125f77  nop
0x180125f78  lea     rcx, [rsp+68h+var_30]
0x180125f7d  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x180125f82  inc     rsi
0x180125f85  jmp     loc_180125DD9
0x180125f8a  mov     rcx, [rsp+68h+arg_18]
0x180125f92  mov     rax, [rcx]
0x180125f95  mov     rax, [rax+88h]
0x180125f9c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180125fa1  mov     ebx, eax
0x180125fa3  test    eax, eax
0x180125fa5  jns     short loc_180125FB1
0x180125fa7  mov     edx, 0D1h
0x180125fac  jmp     loc_180125D9A
0x180125fb1  mov     rcx, [rsp+68h+arg_18]
0x180125fb9  mov     rax, [rcx]
0x180125fbc  mov     rax, [rax+70h]
0x180125fc0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180125fc5  mov     ebx, eax
0x180125fc7  test    eax, eax
0x180125fc9  jns     short loc_180125FD5
0x180125fcb  mov     edx, 0D2h
0x180125fd0  jmp     loc_180125D9A
0x180125fd5  mov     rcx, [rsp+68h+arg_18]
0x180125fdd  mov     rax, [rcx]
0x180125fe0  mov     rax, [rax+0F8h]
0x180125fe7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180125fec  mov     ebx, eax
0x180125fee  test    eax, eax
0x180125ff0  jns     short loc_180125FFC
0x180125ff2  mov     edx, 0D3h
0x180125ff7  jmp     loc_180125D9A
0x180125ffc  lea     rcx, [rsp+68h+arg_18]
0x180126004  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x180126009  nop
0x18012600a  lea     rcx, [rsp+68h+ppstm]
0x18012600f  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x180126014  nop
0x180126015  mov     rcx, rdi
0x180126018  call    ?_Tidy@?$vector@PEAXV?$allocator@PEAX@std@@@std@@AEAAXXZ; std::vector<void *>::_Tidy(void)
0x18012601d  xor     eax, eax
0x18012601f  jmp     short loc_18012604B
0x180126021  lea     rcx, [rsp+68h+arg_18]
0x180126029  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x18012602e  nop
0x18012602f  lea     rcx, [rsp+68h+ppstm]
0x180126034  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x180126039  nop
0x18012603a  mov     rcx, [rsp+68h+arg_0]
0x18012603f  call    ?_Tidy@?$vector@PEAXV?$allocator@PEAX@std@@@std@@AEAAXXZ; std::vector<void *>::_Tidy(void)
0x180126044  mov     eax, dword ptr [rsp+68h+arg_10]
0x18012604b  add     rsp, 50h
0x18012604f  pop     rdi
0x180126050  pop     rsi
0x180126051  pop     rbx
0x180126052  retn
```
