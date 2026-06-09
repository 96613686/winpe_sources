# Microsoft::Windows::Mdm::MdmDiagnosticSource::PolicyDiagDataSource::GetDiagnosticData(IStream * *)

- ea: `0x180115cc0`
- end: `0x180115dea`
- name: `?GetDiagnosticData@PolicyDiagDataSource@MdmDiagnosticSource@Mdm@Windows@Microsoft@@UEAAJPEAPEAUIStream@@@Z`
- size: `298`
- prototype: `__int64 __fastcall(Microsoft::Windows::Mdm::MdmDiagnosticSource::PolicyDiagDataSource *__hidden this, struct IStream **)`
- caller_count: `0`
- callee_count: `9`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x1800ead14`
- `0x1800ece5c`
- `0x1800f7f10`
- `0x1800f8680`
- `0x1800f8708`
- `0x180115cc0`
- `0x180115df0`
- `0x180115e38`
- `0x180122018`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x180115cfd`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x180115cfd`
- `api-ms-win-shcore-stream-l1-1-0!SHCreateMemStream` at `0x180115d64`
- `api-ms-win-shcore-stream-l1-1-0!SHCreateMemStream` at `0x180115d64`

## string_xrefs

- `0x180115d45`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\dll\policydiagdata.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall Microsoft::Windows::Mdm::MdmDiagnosticSource::PolicyDiagDataSource::GetDiagnosticData(
        Microsoft::Windows::Mdm::MdmDiagnosticSource::PolicyDiagDataSource *this,
        struct IStream **a2)
{
  HRESULT DiagnosticData; // eax
  __int64 v5; // rcx
  unsigned int v6; // ebx
  __int64 v7; // rdx
  __int64 Template; // rax
  unsigned __int64 v9; // rdx
  unsigned __int64 v10; // rcx
  __int64 v11; // rcx
  const BYTE *v12; // rax
  IStream *v13; // rax
  int inserted; // eax
  __int64 v15; // rcx
  UINT cbInit[2]; // [rsp+20h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+18h]
  LPSTREAM ppstm; // [rsp+60h] [rbp+30h] BYREF
  struct IStream *v20; // [rsp+68h] [rbp+38h] BYREF

  v20 = 0;
  ppstm = 0;
  *(_QWORD *)cbInit = 0;
  Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&ppstm);
  DiagnosticData = CreateStreamOnHGlobal(0, 1, &ppstm);
  v6 = DiagnosticData;
  if ( DiagnosticData < 0 )
  {
    v7 = 523;
LABEL_7:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v7,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmdiagnostics\\dll\\policydiagdata.cpp",
      (const char *)(unsigned int)DiagnosticData,
      cbInit[0]);
    goto LABEL_14;
  }
  LOBYTE(v5) = *((_BYTE *)this + 2116);
  Template = GetTemplate(v5);
  v10 = -1;
  do
    ++v10;
  while ( *(_WORD *)(Template + 2 * v10 + 2) );
  DiagnosticData = ULongLongMult(v10, v9, (unsigned __int64 *)cbInit);
  v6 = DiagnosticData;
  if ( DiagnosticData < 0 )
  {
    v7 = 524;
    goto LABEL_7;
  }
  LOBYTE(v11) = *((_BYTE *)this + 2116);
  v12 = (const BYTE *)GetTemplate(v11);
  v13 = SHCreateMemStream(v12, cbInit[0]);
  Microsoft::WRL::ComPtr<IStream>::operator=(&v20, v13);
  DiagnosticData = CreateDiagnosticData(v20, ppstm);
  v6 = DiagnosticData;
  if ( DiagnosticData < 0 )
  {
    v7 = 529;
    goto LABEL_7;
  }
  inserted = Microsoft::Windows::Mdm::MdmDiagnosticSource::PolicyDiagDataSource::InsertRedirectedRegKeyData(
               this,
               ppstm,
               a2);
  v6 = inserted;
  if ( inserted >= 0 )
  {
    v6 = 0;
  }
  else if ( (Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits & 8) != 0 )
  {
    McTemplateU0d_EventWriteTransfer(
      v15,
      EnterpriseDiagnosticsMdmDiagnosticsInsertRedirectedRegKeyFailure,
      (unsigned int)inserted);
  }
LABEL_14:
  Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&ppstm);
  Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&v20);
  return v6;
}

```

## disassembly

```asm
0x180115cc0  mov     [rsp-18h+arg_0], rbx
0x180115cc5  mov     [rsp-18h+arg_8], rsi
0x180115cca  push    rbp
0x180115ccb  push    rdi
0x180115ccc  push    r14
0x180115cce  mov     rbp, rsp
0x180115cd1  sub     rsp, 30h
0x180115cd5  mov     rsi, rdx
0x180115cd8  mov     rdi, rcx
0x180115cdb  xor     r14d, r14d
0x180115cde  mov     [rbp+arg_18], r14
0x180115ce2  mov     [rbp+ppstm], r14
0x180115ce6  mov     qword ptr [rbp+cbInit], r14
0x180115cea  lea     rcx, [rbp+ppstm]
0x180115cee  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x180115cf3  lea     r8, [rbp+ppstm]; ppstm
0x180115cf7  lea     edx, [r14+1]; fDeleteOnRelease
0x180115cfb  xor     ecx, ecx; hGlobal
0x180115cfd  call    cs:__imp_CreateStreamOnHGlobal
0x180115d03  mov     ebx, eax
0x180115d05  test    eax, eax
0x180115d07  jns     short loc_180115D10
0x180115d09  mov     edx, 20Bh
0x180115d0e  jmp     short loc_180115D3E
0x180115d10  mov     cl, [rdi+844h]
0x180115d16  call    GetTemplate
0x180115d1b  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180115d1f  inc     rcx; unsigned __int64
0x180115d22  cmp     [rax+rcx*2+2], r14w
0x180115d28  jnz     short loc_180115D1F
0x180115d2a  lea     r8, [rbp+cbInit]; unsigned __int64 *
0x180115d2e  call    ?ULongLongMult@@YAJ_K0PEA_K@Z; ULongLongMult(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x180115d33  mov     ebx, eax
0x180115d35  test    eax, eax
0x180115d37  jns     short loc_180115D53
0x180115d39  mov     edx, 20Ch; void *
0x180115d3e  mov     rcx, [rbp+18h]; this
0x180115d42  mov     r9d, eax; char *
0x180115d45  lea     r8, aOnecoreuapAdmi_5; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x180115d4c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180115d51  jmp     short loc_180115DC2
0x180115d53  mov     cl, [rdi+844h]
0x180115d59  call    GetTemplate
0x180115d5e  mov     rcx, rax; pInit
0x180115d61  mov     edx, [rbp+cbInit]; cbInit
0x180115d64  call    cs:__imp_SHCreateMemStream
0x180115d6a  mov     rdx, rax
0x180115d6d  lea     rcx, [rbp+arg_18]
0x180115d71  call    ??4?$ComPtr@UIStream@@@WRL@Microsoft@@QEAAAEAV012@PEAUIStream@@@Z; Microsoft::WRL::ComPtr<IStream>::operator=(IStream *)
0x180115d76  mov     rdx, [rbp+ppstm]; struct IStream *
0x180115d7a  mov     rcx, [rbp+arg_18]; struct IStream *
0x180115d7e  call    ?CreateDiagnosticData@@YAJPEAUIStream@@0@Z; CreateDiagnosticData(IStream *,IStream *)
0x180115d83  mov     ebx, eax
0x180115d85  test    eax, eax
0x180115d87  jns     short loc_180115D90
0x180115d89  mov     edx, 211h
0x180115d8e  jmp     short loc_180115D3E
0x180115d90  mov     r8, rsi; struct IStream **
0x180115d93  mov     rdx, [rbp+ppstm]; struct IStream *
0x180115d97  mov     rcx, rdi; this
0x180115d9a  call    ?InsertRedirectedRegKeyData@PolicyDiagDataSource@MdmDiagnosticSource@Mdm@Windows@Microsoft@@AEAAJPEAUIStream@@PEAPEAU6@@Z; Microsoft::Windows::Mdm::MdmDiagnosticSource::PolicyDiagDataSource::InsertRedirectedRegKeyData(IStream *,IStream * *)
0x180115d9f  mov     ebx, eax
0x180115da1  test    eax, eax
0x180115da3  jns     short loc_180115DBF
0x180115da5  test    cs:Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits, 8
0x180115dac  jz      short loc_180115DC2
0x180115dae  mov     r8d, eax
0x180115db1  lea     rdx, EnterpriseDiagnosticsMdmDiagnosticsInsertRedirectedRegKeyFailure
0x180115db8  call    McTemplateU0d_EventWriteTransfer
0x180115dbd  jmp     short loc_180115DC2
0x180115dbf  mov     ebx, r14d
0x180115dc2  lea     rcx, [rbp+ppstm]
0x180115dc6  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x180115dcb  nop
0x180115dcc  lea     rcx, [rbp+arg_18]
0x180115dd0  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x180115dd5  mov     eax, ebx
0x180115dd7  mov     rbx, [rsp+30h+arg_0]
0x180115ddc  mov     rsi, [rsp+30h+arg_8]
0x180115de1  add     rsp, 30h
0x180115de5  pop     r14
0x180115de7  pop     rdi
0x180115de8  pop     rbp
0x180115de9  retn
```
