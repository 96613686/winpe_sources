# Microsoft::Windows::Mdm::MdmDiagnosticSource::SCEPDiagDataSource::GetDiagnosticData(IStream * *)

- ea: `0x180116a80`
- end: `0x180116b72`
- name: `?GetDiagnosticData@SCEPDiagDataSource@MdmDiagnosticSource@Mdm@Windows@Microsoft@@UEAAJPEAPEAUIStream@@@Z`
- size: `242`
- prototype: `int(Microsoft::Windows::Mdm::MdmDiagnosticSource::SCEPDiagDataSource *__hidden this, struct IStream **)`
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x1800ead14`
- `0x1800ece5c`
- `0x1800f7f10`
- `0x1800f8680`
- `0x180116a80`
- `0x180122018`

## import_xrefs

- `ntdll!RtlIsStateSeparationEnabled` at `0x180116ab9`
- `ntdll!RtlIsStateSeparationEnabled` at `0x180116b11`
- `ntdll!RtlIsStateSeparationEnabled` at `0x180116ab9`
- `ntdll!RtlIsStateSeparationEnabled` at `0x180116b11`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x180116aa8`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x180116aa8`
- `api-ms-win-shcore-stream-l1-1-0!SHCreateMemStream` at `0x180116b24`
- `api-ms-win-shcore-stream-l1-1-0!SHCreateMemStream` at `0x180116b24`

## string_xrefs

- `0x180116ac6`: `<?xml version="1.0" encoding="utf-16"?>\n<DiagData>\n  <DataSource name="OSDataSCEP">\n    <Key><Category>MdmServerClientCert</Category><Path>HKCU\Software\Microsoft\SCEP\*</Path>\n      <Representation>ServerName</Representation>\n      <Key>\n        <Category>Identifier</Category>\n        <Path>*</Path>\n        <Representation>ID</Representation>\n        <Value>\n          <Name>CertificateThumbPrint</Name>\n          <ValueRepresentation>CertThumbPrint</ValueRepresentation>\n        </Val`
- `0x180116abf`: `<?xml version="1.0" encoding="utf-16"?>\n<DiagData>\n  <DataSource name="SCEP">\n    <Key>\n      <Category>MdmServerClientCert</Category>\n      <Path>HKCU\Software\Microsoft\SCEP\*</Path>\n      <Representation>ServerName</Representation>\n      <Key>\n        <Category>Identifier</Category>\n        <Path>*</Path>\n        <Representation>ID</Representation>\n        <Value>\n          <Name>CertificateThumbPrint</Name>\n          <ValueRepresentation>CertThumbPrint</ValueRepresentation>\n   `
- `0x180116b03`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\dll\scepdiagdata.cpp`

## pseudocode

```c
__int64 __fastcall Microsoft::Windows::Mdm::MdmDiagnosticSource::SCEPDiagDataSource::GetDiagnosticData(
        Microsoft::Windows::Mdm::MdmDiagnosticSource::SCEPDiagDataSource *this,
        struct IStream **a2)
{
  HRESULT StreamOnHGlobal; // eax
  unsigned int v4; // ebx
  __int64 v5; // rdx
  char IsStateSeparationEnabled; // al
  const BYTE *v7; // rdi
  const wchar_t *v8; // rdx
  __int64 v9; // rcx
  IStream *v10; // rax
  int v12; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  struct IStream *v14; // [rsp+50h] [rbp+18h] BYREF
  unsigned __int64 cbInit; // [rsp+58h] [rbp+20h] BYREF

  v14 = 0;
  cbInit = 0;
  StreamOnHGlobal = CreateStreamOnHGlobal(0, 1, a2);
  v4 = StreamOnHGlobal;
  if ( StreamOnHGlobal >= 0 )
  {
    IsStateSeparationEnabled = RtlIsStateSeparationEnabled();
    v7 = (const BYTE *)aXmlVersion10En_25;
    v8 = aXmlVersion10En_25;
    if ( !IsStateSeparationEnabled )
      v8 = (const wchar_t *)aXmlVersion10En_4;
    v9 = -1;
    do
      ++v9;
    while ( v8[v9] );
    StreamOnHGlobal = ULongLongMult(v9 + 1, (unsigned __int64)v8, &cbInit);
    v4 = StreamOnHGlobal;
    if ( StreamOnHGlobal >= 0 )
    {
      if ( !(unsigned __int8)RtlIsStateSeparationEnabled() )
        v7 = aXmlVersion10En_4;
      v10 = SHCreateMemStream(v7, cbInit);
      Microsoft::WRL::ComPtr<IStream>::operator=(&v14, v10);
      StreamOnHGlobal = CreateDiagnosticData(v14, *a2);
      v4 = StreamOnHGlobal;
      if ( StreamOnHGlobal >= 0 )
      {
        v4 = 0;
        goto LABEL_15;
      }
      v5 = 55;
    }
    else
    {
      v5 = 50;
    }
  }
  else
  {
    v5 = 49;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v5,
    (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmdiagnostics\\dll\\scepdiagdata.cpp",
    (const char *)(unsigned int)StreamOnHGlobal,
    v12);
LABEL_15:
  Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&v14);
  return v4;
}

```

## disassembly

```asm
0x180116a80  mov     rax, rsp
0x180116a83  mov     [rax+8], rbx
0x180116a87  mov     [rax+10h], rbp
0x180116a8b  push    rsi
0x180116a8c  push    rdi
0x180116a8d  push    r14; int
0x180116a8f  sub     rsp, 20h
0x180116a93  mov     rsi, rdx
0x180116a96  xor     ebp, ebp
0x180116a98  mov     [rax+18h], rbp
0x180116a9c  mov     [rax+20h], rbp
0x180116aa0  mov     r8, rdx; ppstm
0x180116aa3  lea     edx, [rbp+1]; fDeleteOnRelease
0x180116aa6  xor     ecx, ecx; hGlobal
0x180116aa8  call    cs:__imp_CreateStreamOnHGlobal
0x180116aae  mov     ebx, eax
0x180116ab0  test    eax, eax
0x180116ab2  jns     short loc_180116AB9
0x180116ab4  lea     edx, [rbp+31h]
0x180116ab7  jmp     short loc_180116AFB
0x180116ab9  call    cs:__imp_RtlIsStateSeparationEnabled
0x180116abf  lea     r14, aXmlVersion10En_4; "<?xml version=\"1.0\" encoding=\"utf-16"...
0x180116ac6  lea     rdi, aXmlVersion10En_25; "<?xml version=\"1.0\" encoding=\"utf-16"...
0x180116acd  mov     rdx, rdi
0x180116ad0  test    al, al
0x180116ad2  cmovz   rdx, r14; unsigned __int64
0x180116ad6  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180116ada  inc     rcx
0x180116add  cmp     [rdx+rcx*2], bp
0x180116ae1  jnz     short loc_180116ADA
0x180116ae3  inc     rcx; unsigned __int64
0x180116ae6  lea     r8, [rsp+38h+cbInit]; unsigned __int64 *
0x180116aeb  call    ?ULongLongMult@@YAJ_K0PEA_K@Z; ULongLongMult(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x180116af0  mov     ebx, eax
0x180116af2  test    eax, eax
0x180116af4  jns     short loc_180116B11
0x180116af6  mov     edx, 32h ; '2'; void *
0x180116afb  mov     rcx, [rsp+38h]; this
0x180116b00  mov     r9d, eax; char *
0x180116b03  lea     r8, aOnecoreuapAdmi_17; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x180116b0a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180116b0f  jmp     short loc_180116B53
0x180116b11  call    cs:__imp_RtlIsStateSeparationEnabled
0x180116b17  test    al, al
0x180116b19  cmovz   rdi, r14
0x180116b1d  mov     edx, dword ptr [rsp+38h+cbInit]; cbInit
0x180116b21  mov     rcx, rdi; pInit
0x180116b24  call    cs:__imp_SHCreateMemStream
0x180116b2a  mov     rdx, rax
0x180116b2d  lea     rcx, [rsp+38h+arg_10]
0x180116b32  call    ??4?$ComPtr@UIStream@@@WRL@Microsoft@@QEAAAEAV012@PEAUIStream@@@Z; Microsoft::WRL::ComPtr<IStream>::operator=(IStream *)
0x180116b37  mov     rdx, [rsi]; struct IStream *
0x180116b3a  mov     rcx, [rsp+38h+arg_10]; struct IStream *
0x180116b3f  call    ?CreateDiagnosticData@@YAJPEAUIStream@@0@Z; CreateDiagnosticData(IStream *,IStream *)
0x180116b44  mov     ebx, eax
0x180116b46  test    eax, eax
0x180116b48  jns     short loc_180116B51
0x180116b4a  mov     edx, 37h ; '7'
0x180116b4f  jmp     short loc_180116AFB
0x180116b51  mov     ebx, ebp
0x180116b53  lea     rcx, [rsp+38h+arg_10]
0x180116b58  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x180116b5d  mov     eax, ebx
0x180116b5f  mov     rbx, [rsp+38h+arg_0]
0x180116b64  mov     rbp, [rsp+38h+arg_8]
0x180116b69  add     rsp, 20h
0x180116b6d  pop     r14
0x180116b6f  pop     rdi
0x180116b70  pop     rsi
0x180116b71  retn
```
