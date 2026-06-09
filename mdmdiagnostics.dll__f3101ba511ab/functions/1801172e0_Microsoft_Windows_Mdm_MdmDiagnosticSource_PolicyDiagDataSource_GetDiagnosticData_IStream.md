# Microsoft::Windows::Mdm::MdmDiagnosticSource::PolicyDiagDataSource::GetDiagnosticData(IStream * *)

- ea: `0x1801172e0`
- end: `0x180117417`
- name: `?GetDiagnosticData@PolicyDiagDataSource@MdmDiagnosticSource@Mdm@Windows@Microsoft@@UEAAJPEAPEAUIStream@@@Z`
- size: `311`
- prototype: `__int64 __fastcall(Microsoft::Windows::Mdm::MdmDiagnosticSource::PolicyDiagDataSource *__hidden this, struct IStream **)`
- caller_count: `0`
- callee_count: `9`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x1800eb1ac`
- `0x1800ed46c`
- `0x1800f8e70`
- `0x1800f962c`
- `0x1800f96c0`
- `0x1801172e0`
- `0x180117420`
- `0x180117474`
- `0x180123aa8`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x18011731d`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x18011731d`
- `api-ms-win-shcore-stream-l1-1-0!SHCreateMemStream` at `0x18011738a`
- `api-ms-win-shcore-stream-l1-1-0!SHCreateMemStream` at `0x18011738a`

## string_xrefs

- `0x18011736b`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\dll\policydiagdata.cpp`

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
0x1801172e0  mov     [rsp-18h+arg_0], rbx
0x1801172e5  mov     [rsp-18h+arg_8], rsi
0x1801172ea  push    rbp
0x1801172eb  push    rdi
0x1801172ec  push    r14
0x1801172ee  mov     rbp, rsp
0x1801172f1  sub     rsp, 30h
0x1801172f5  mov     rsi, rdx
0x1801172f8  mov     rdi, rcx
0x1801172fb  xor     r14d, r14d
0x1801172fe  mov     [rbp+arg_18], r14
0x180117302  mov     [rbp+ppstm], r14
0x180117306  mov     qword ptr [rbp+cbInit], r14
0x18011730a  lea     rcx, [rbp+ppstm]
0x18011730e  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x180117313  lea     r8, [rbp+ppstm]; ppstm
0x180117317  lea     edx, [r14+1]; fDeleteOnRelease
0x18011731b  xor     ecx, ecx; hGlobal
0x18011731d  call    cs:__imp_CreateStreamOnHGlobal
0x180117324  nop     dword ptr [rax+rax+00h]
0x180117329  mov     ebx, eax
0x18011732b  test    eax, eax
0x18011732d  jns     short loc_180117336
0x18011732f  mov     edx, 20Bh
0x180117334  jmp     short loc_180117364
0x180117336  mov     cl, [rdi+844h]
0x18011733c  call    GetTemplate
0x180117341  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180117345  inc     rcx; unsigned __int64
0x180117348  cmp     [rax+rcx*2+2], r14w
0x18011734e  jnz     short loc_180117345
0x180117350  lea     r8, [rbp+cbInit]; unsigned __int64 *
0x180117354  call    ?ULongLongMult@@YAJ_K0PEA_K@Z; ULongLongMult(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x180117359  mov     ebx, eax
0x18011735b  test    eax, eax
0x18011735d  jns     short loc_180117379
0x18011735f  mov     edx, 20Ch; void *
0x180117364  mov     rcx, [rbp+18h]; this
0x180117368  mov     r9d, eax; char *
0x18011736b  lea     r8, aOnecoreuapAdmi_5; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x180117372  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180117377  jmp     short loc_1801173EE
0x180117379  mov     cl, [rdi+844h]
0x18011737f  call    GetTemplate
0x180117384  mov     rcx, rax; pInit
0x180117387  mov     edx, [rbp+cbInit]; cbInit
0x18011738a  call    cs:__imp_SHCreateMemStream
0x180117391  nop     dword ptr [rax+rax+00h]
0x180117396  mov     rdx, rax
0x180117399  lea     rcx, [rbp+arg_18]
0x18011739d  call    ??4?$ComPtr@UIStream@@@WRL@Microsoft@@QEAAAEAV012@PEAUIStream@@@Z; Microsoft::WRL::ComPtr<IStream>::operator=(IStream *)
0x1801173a2  mov     rdx, [rbp+ppstm]; struct IStream *
0x1801173a6  mov     rcx, [rbp+arg_18]; struct IStream *
0x1801173aa  call    ?CreateDiagnosticData@@YAJPEAUIStream@@0@Z; CreateDiagnosticData(IStream *,IStream *)
0x1801173af  mov     ebx, eax
0x1801173b1  test    eax, eax
0x1801173b3  jns     short loc_1801173BC
0x1801173b5  mov     edx, 211h
0x1801173ba  jmp     short loc_180117364
0x1801173bc  mov     r8, rsi; struct IStream **
0x1801173bf  mov     rdx, [rbp+ppstm]; struct IStream *
0x1801173c3  mov     rcx, rdi; this
0x1801173c6  call    ?InsertRedirectedRegKeyData@PolicyDiagDataSource@MdmDiagnosticSource@Mdm@Windows@Microsoft@@AEAAJPEAUIStream@@PEAPEAU6@@Z; Microsoft::Windows::Mdm::MdmDiagnosticSource::PolicyDiagDataSource::InsertRedirectedRegKeyData(IStream *,IStream * *)
0x1801173cb  mov     ebx, eax
0x1801173cd  test    eax, eax
0x1801173cf  jns     short loc_1801173EB
0x1801173d1  test    cs:Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits, 8
0x1801173d8  jz      short loc_1801173EE
0x1801173da  mov     r8d, eax
0x1801173dd  lea     rdx, EnterpriseDiagnosticsMdmDiagnosticsInsertRedirectedRegKeyFailure
0x1801173e4  call    McTemplateU0d_EventWriteTransfer
0x1801173e9  jmp     short loc_1801173EE
0x1801173eb  mov     ebx, r14d
0x1801173ee  lea     rcx, [rbp+ppstm]
0x1801173f2  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x1801173f7  nop
0x1801173f8  lea     rcx, [rbp+arg_18]
0x1801173fc  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x180117401  mov     eax, ebx
0x180117403  mov     rbx, [rsp+30h+arg_0]
0x180117408  mov     rsi, [rsp+30h+arg_8]
0x18011740d  add     rsp, 30h
0x180117411  pop     r14
0x180117413  pop     rdi
0x180117414  pop     rbp
0x180117415  retn
```
