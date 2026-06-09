# CreateDiagnosticReportFromStreams(std::vector<IStream *,std::allocator<IStream *>>,ushort const *)

- ea: `0x180127638`
- end: `0x180127a6e`
- name: `?CreateDiagnosticReportFromStreams@@YAJV?$vector@PEAUIStream@@V?$allocator@PEAUIStream@@@std@@@std@@PEBG@Z`
- size: `1078`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800fbe40`

## callees

- `0x1800eb1ac`
- `0x1800ed46c`
- `0x1800efb28`
- `0x1800f8e70`
- `0x180105744`
- `0x180127638`
- `0x180127a74`
- `0x180127be4`
- `0x180127cb8`
- `0x180127d94`
- `0x180193010`

## import_xrefs

- `api-ms-win-shcore-stream-l1-1-0!SHCreateStreamOnFileW` at `0x18012769c`
- `api-ms-win-shcore-stream-l1-1-0!SHCreateStreamOnFileW` at `0x18012769c`

## string_xrefs

- `0x1801276b6`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\reportfromstreams\registrydiagnosticreportfromstream.cpp`
- `0x1801277b7`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\reportfromstreams\registrydiagnosticreportfromstream.cpp`
- `0x1801278bb`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\reportfromstreams\registrydiagnosticreportfromstream.cpp`
- `0x180127931`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\reportfromstreams\registrydiagnosticreportfromstream.cpp`

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
0x180127638  mov     [rsp+arg_0], rcx
0x18012763d  push    rbx
0x18012763e  push    rsi
0x18012763f  push    rdi
0x180127640  sub     rsp, 50h
0x180127644  mov     rsi, rdx
0x180127647  mov     rdi, rcx
0x18012764a  mov     [rsp+68h+ppstm], 0
0x180127653  mov     rcx, rdx; unsigned __int16 *
0x180127656  call    ?EnsureDirectoriesArePresent@@YAJPEBG@Z; EnsureDirectoriesArePresent(ushort const *)
0x18012765b  mov     ebx, eax
0x18012765d  test    eax, eax
0x18012765f  jns     short loc_180127685
0x180127661  test    cs:Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits, 8
0x180127668  jz      loc_1801277D7
0x18012766e  mov     r9d, eax
0x180127671  mov     r8, rsi
0x180127674  lea     rdx, EnterpriseDiagnosticsMdmDiagnosticsCreatingOrCheckingDirectoryFailure
0x18012767b  call    McTemplateU0zd_EventWriteTransfer
0x180127680  jmp     loc_1801277D7
0x180127685  lea     rcx, [rsp+68h+ppstm]
0x18012768a  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x18012768f  lea     r8, [rsp+68h+ppstm]; ppstm
0x180127694  mov     edx, 1001h; grfMode
0x180127699  mov     rcx, rsi; pszFile
0x18012769c  call    cs:__imp_SHCreateStreamOnFileW
0x1801276a3  nop     dword ptr [rax+rax+00h]
0x1801276a8  mov     ebx, eax
0x1801276aa  test    eax, eax
0x1801276ac  jns     short loc_1801276CC
0x1801276ae  mov     rcx, [rsp+68h]; this
0x1801276b3  mov     r9d, eax; char *
0x1801276b6  lea     r8, aOnecoreuapAdmi_8; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x1801276bd  mov     edx, 0B0h; void *
0x1801276c2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801276c7  jmp     loc_1801277D7
0x1801276cc  mov     [rsp+68h+arg_18], 0
0x1801276d8  lea     rcx, [rsp+68h+arg_18]
0x1801276e0  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x1801276e5  lea     rdx, [rsp+68h+arg_18]; struct IXmlWriter **
0x1801276ed  mov     rcx, [rsp+68h+ppstm]; struct IStream *
0x1801276f2  call    ?InitializeReportGeneration@@YAJPEAUIStream@@PEAPEAUIXmlWriter@@@Z; InitializeReportGeneration(IStream *,IXmlWriter * *)
0x1801276f7  mov     ebx, eax
0x1801276f9  test    eax, eax
0x1801276fb  jns     short loc_180127707
0x1801276fd  mov     edx, 0B3h
0x180127702  jmp     loc_1801277B4
0x180127707  mov     rcx, [rsp+68h+arg_18]
0x18012770f  mov     rax, [rcx]
0x180127712  xor     r9d, r9d
0x180127715  lea     r8, aMdmenterprised; "MDMEnterpriseDiagnosticsReport"
0x18012771c  xor     edx, edx
0x18012771e  mov     rax, [rax+0D8h]
0x180127725  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18012772a  mov     ebx, eax
0x18012772c  test    eax, eax
0x18012772e  jns     short loc_180127737
0x180127730  mov     edx, 0B5h
0x180127735  jmp     short loc_1801277B4
0x180127737  mov     rcx, [rsp+68h+arg_18]
0x18012773f  mov     rax, [rcx]
0x180127742  xor     r9d, r9d
0x180127745  lea     r8, aVersion; "Version"
0x18012774c  xor     edx, edx
0x18012774e  mov     rax, [rax+0D8h]
0x180127755  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18012775a  mov     ebx, eax
0x18012775c  test    eax, eax
0x18012775e  jns     short loc_180127767
0x180127760  mov     edx, 0B6h
0x180127765  jmp     short loc_1801277B4
0x180127767  mov     rcx, [rsp+68h+arg_18]
0x18012776f  mov     rax, [rcx]
0x180127772  lea     rdx, a10_1; "1.0"
0x180127779  mov     rax, [rax+0E0h]
0x180127780  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180127785  mov     ebx, eax
0x180127787  test    eax, eax
0x180127789  jns     short loc_180127792
0x18012778b  mov     edx, 0B7h
0x180127790  jmp     short loc_1801277B4
0x180127792  mov     rcx, [rsp+68h+arg_18]
0x18012779a  mov     rax, [rcx]
0x18012779d  mov     rax, [rax+88h]
0x1801277a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801277a9  mov     ebx, eax
0x1801277ab  test    eax, eax
0x1801277ad  jns     short loc_1801277F1
0x1801277af  mov     edx, 0B8h; void *
0x1801277b4  mov     r9d, eax; char *
0x1801277b7  lea     r8, aOnecoreuapAdmi_8; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x1801277be  mov     rcx, [rsp+68h]; this
0x1801277c3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801277c8  nop
0x1801277c9  lea     rcx, [rsp+68h+arg_18]
0x1801277d1  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x1801277d6  nop
0x1801277d7  lea     rcx, [rsp+68h+ppstm]
0x1801277dc  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x1801277e1  nop
0x1801277e2  mov     rcx, rdi
0x1801277e5  call    ?_Tidy@?$vector@PEAXV?$allocator@PEAX@std@@@std@@AEAAXXZ; std::vector<void *>::_Tidy(void)
0x1801277ea  mov     eax, ebx
0x1801277ec  jmp     loc_180127A65
0x1801277f1  xor     esi, esi
0x1801277f3  mov     rdx, [rdi]
0x1801277f6  mov     rax, [rdi+8]
0x1801277fa  sub     rax, rdx
0x1801277fd  sar     rax, 3
0x180127801  cmp     rsi, rax
0x180127804  jnb     loc_1801279A4
0x18012780a  mov     [rsp+68h+var_30], 0
0x180127813  mov     rdx, [rdx+rsi*8]
0x180127817  lea     rcx, [rsp+68h+var_30]
0x18012781c  call    ??4?$ComPtr@UIStream@@@WRL@Microsoft@@QEAAAEAV012@PEAUIStream@@@Z; Microsoft::WRL::ComPtr<IStream>::operator=(IStream *)
0x180127821  mov     rbx, [rsp+68h+var_30]
0x180127826  test    rbx, rbx
0x180127829  jnz     short loc_180127861
0x18012782b  lea     rcx, [rsp+68h+var_30]
0x180127830  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x180127835  nop
0x180127836  lea     rcx, [rsp+68h+arg_18]
0x18012783e  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x180127843  nop
0x180127844  lea     rcx, [rsp+68h+ppstm]
0x180127849  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x18012784e  nop
0x18012784f  mov     rcx, rdi
0x180127852  call    ?_Tidy@?$vector@PEAXV?$allocator@PEAX@std@@@std@@AEAAXXZ; std::vector<void *>::_Tidy(void)
0x180127857  mov     eax, 80070057h
0x18012785c  jmp     loc_180127A65
0x180127861  mov     [rsp+68h+arg_10], 0
0x18012786d  mov     [rsp+68h+var_28], 0
0x180127876  mov     rax, [rbx]
0x180127879  xor     r9d, r9d
0x18012787c  xor     r8d, r8d
0x18012787f  mov     rdx, [rsp+68h+var_28]
0x180127884  mov     rcx, rbx
0x180127887  mov     rax, [rax+28h]
0x18012788b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180127890  lea     rcx, [rsp+68h+arg_10]
0x180127898  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x18012789d  lea     rdx, [rsp+68h+arg_10]; struct IXmlReader **
0x1801278a5  mov     rcx, rbx; struct IStream *
0x1801278a8  call    ?InitializeDataGathering@@YAJPEAUIStream@@PEAPEAUIXmlReader@@@Z; InitializeDataGathering(IStream *,IXmlReader * *)
0x1801278ad  mov     ebx, eax
0x1801278af  test    eax, eax
0x1801278b1  jns     short loc_18012790E
0x1801278b3  mov     rcx, [rsp+68h]; this
0x1801278b8  mov     r9d, eax; char *
0x1801278bb  lea     r8, aOnecoreuapAdmi_8; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x1801278c2  mov     edx, 0CBh; void *
0x1801278c7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801278cc  nop
0x1801278cd  lea     rcx, [rsp+68h+arg_10]
0x1801278d5  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x1801278da  nop
0x1801278db  lea     rcx, [rsp+68h+var_30]
0x1801278e0  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x1801278e5  nop
0x1801278e6  lea     rcx, [rsp+68h+arg_18]
0x1801278ee  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x1801278f3  nop
0x1801278f4  lea     rcx, [rsp+68h+ppstm]
0x1801278f9  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x1801278fe  nop
0x1801278ff  mov     rcx, rdi
0x180127902  call    ?_Tidy@?$vector@PEAXV?$allocator@PEAX@std@@@std@@AEAAXXZ; std::vector<void *>::_Tidy(void)
0x180127907  mov     eax, ebx
0x180127909  jmp     loc_180127A65
0x18012790e  mov     rdx, [rsp+68h+arg_18]; struct IXmlWriter *
0x180127916  mov     rcx, [rsp+68h+arg_10]; struct IXmlReader *
0x18012791e  call    ?GenerateReport@@YAJPEAUIXmlReader@@PEAUIXmlWriter@@@Z; GenerateReport(IXmlReader *,IXmlWriter *)
0x180127923  mov     ebx, eax
0x180127925  test    eax, eax
0x180127927  jns     short loc_180127984
0x180127929  mov     rcx, [rsp+68h]; this
0x18012792e  mov     r9d, eax; char *
0x180127931  lea     r8, aOnecoreuapAdmi_8; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x180127938  mov     edx, 0CCh; void *
0x18012793d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180127942  nop
0x180127943  lea     rcx, [rsp+68h+arg_10]
0x18012794b  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x180127950  nop
0x180127951  lea     rcx, [rsp+68h+var_30]
0x180127956  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x18012795b  nop
0x18012795c  lea     rcx, [rsp+68h+arg_18]
0x180127964  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x180127969  nop
0x18012796a  lea     rcx, [rsp+68h+ppstm]
0x18012796f  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x180127974  nop
0x180127975  mov     rcx, rdi
0x180127978  call    ?_Tidy@?$vector@PEAXV?$allocator@PEAX@std@@@std@@AEAAXXZ; std::vector<void *>::_Tidy(void)
0x18012797d  mov     eax, ebx
0x18012797f  jmp     loc_180127A65
0x180127984  lea     rcx, [rsp+68h+arg_10]
0x18012798c  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x180127991  nop
0x180127992  lea     rcx, [rsp+68h+var_30]
0x180127997  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x18012799c  inc     rsi
0x18012799f  jmp     loc_1801277F3
0x1801279a4  mov     rcx, [rsp+68h+arg_18]
0x1801279ac  mov     rax, [rcx]
0x1801279af  mov     rax, [rax+88h]
0x1801279b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801279bb  mov     ebx, eax
0x1801279bd  test    eax, eax
0x1801279bf  jns     short loc_1801279CB
0x1801279c1  mov     edx, 0D1h
0x1801279c6  jmp     loc_1801277B4
0x1801279cb  mov     rcx, [rsp+68h+arg_18]
0x1801279d3  mov     rax, [rcx]
0x1801279d6  mov     rax, [rax+70h]
0x1801279da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801279df  mov     ebx, eax
0x1801279e1  test    eax, eax
0x1801279e3  jns     short loc_1801279EF
0x1801279e5  mov     edx, 0D2h
0x1801279ea  jmp     loc_1801277B4
0x1801279ef  mov     rcx, [rsp+68h+arg_18]
0x1801279f7  mov     rax, [rcx]
0x1801279fa  mov     rax, [rax+0F8h]
0x180127a01  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180127a06  mov     ebx, eax
0x180127a08  test    eax, eax
0x180127a0a  jns     short loc_180127A16
0x180127a0c  mov     edx, 0D3h
0x180127a11  jmp     loc_1801277B4
0x180127a16  lea     rcx, [rsp+68h+arg_18]
0x180127a1e  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x180127a23  nop
0x180127a24  lea     rcx, [rsp+68h+ppstm]
0x180127a29  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x180127a2e  nop
0x180127a2f  mov     rcx, rdi
0x180127a32  call    ?_Tidy@?$vector@PEAXV?$allocator@PEAX@std@@@std@@AEAAXXZ; std::vector<void *>::_Tidy(void)
0x180127a37  xor     eax, eax
0x180127a39  jmp     short loc_180127A65
0x180127a3b  lea     rcx, [rsp+68h+arg_18]
0x180127a43  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x180127a48  nop
0x180127a49  lea     rcx, [rsp+68h+ppstm]
0x180127a4e  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x180127a53  nop
0x180127a54  mov     rcx, [rsp+68h+arg_0]
0x180127a59  call    ?_Tidy@?$vector@PEAXV?$allocator@PEAX@std@@@std@@AEAAXXZ; std::vector<void *>::_Tidy(void)
0x180127a5e  mov     eax, dword ptr [rsp+68h+arg_10]
0x180127a65  add     rsp, 50h
0x180127a69  pop     rdi
0x180127a6a  pop     rsi
0x180127a6b  pop     rbx
0x180127a6c  retn
```
