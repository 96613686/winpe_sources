# Microsoft::Windows::Mdm::MdmDiagnosticSource::SCEPDiagDataSource::GetDiagnosticData(IStream * *)

- ea: `0x180118150`
- end: `0x18011825b`
- name: `?GetDiagnosticData@SCEPDiagDataSource@MdmDiagnosticSource@Mdm@Windows@Microsoft@@UEAAJPEAPEAUIStream@@@Z`
- size: `267`
- prototype: `int(Microsoft::Windows::Mdm::MdmDiagnosticSource::SCEPDiagDataSource *__hidden this, struct IStream **)`
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x1800eb1ac`
- `0x1800ed46c`
- `0x1800f8e70`
- `0x1800f962c`
- `0x180118150`
- `0x180123aa8`

## import_xrefs

- `ntdll!RtlIsStateSeparationEnabled` at `0x18011818f`
- `ntdll!RtlIsStateSeparationEnabled` at `0x1801181ed`
- `ntdll!RtlIsStateSeparationEnabled` at `0x18011818f`
- `ntdll!RtlIsStateSeparationEnabled` at `0x1801181ed`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x180118178`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x180118178`
- `api-ms-win-shcore-stream-l1-1-0!SHCreateMemStream` at `0x180118206`
- `api-ms-win-shcore-stream-l1-1-0!SHCreateMemStream` at `0x180118206`

## string_xrefs

- `0x18011819b`: `<?xml version="1.0" encoding="utf-16"?>\n<DiagData>\n  <DataSource name="SCEP">\n    <Key>\n      <Category>MdmServerClientCert</Category>\n      <Path>HKCU\Software\Microsoft\SCEP\*</Path>\n      <Representation>ServerName</Representation>\n      <Key>\n        <Category>Identifier</Category>\n        <Path>*</Path>\n        <Representation>ID</Representation>\n        <Value>\n          <Name>CertificateThumbPrint</Name>\n          <ValueRepresentation>CertThumbPrint</ValueRepresentation>\n   `
- `0x1801181a2`: `<?xml version="1.0" encoding="utf-16"?>\n<DiagData>\n  <DataSource name="OSDataSCEP">\n    <Key><Category>MdmServerClientCert</Category><Path>HKCU\Software\Microsoft\SCEP\*</Path>\n      <Representation>ServerName</Representation>\n      <Key>\n        <Category>Identifier</Category>\n        <Path>*</Path>\n        <Representation>ID</Representation>\n        <Value>\n          <Name>CertificateThumbPrint</Name>\n          <ValueRepresentation>CertThumbPrint</ValueRepresentation>\n        </Val`
- `0x1801181df`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\dll\scepdiagdata.cpp`

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
0x180118150  mov     rax, rsp
0x180118153  mov     [rax+8], rbx
0x180118157  mov     [rax+10h], rbp
0x18011815b  push    rsi
0x18011815c  push    rdi
0x18011815d  push    r14; int
0x18011815f  sub     rsp, 20h
0x180118163  mov     rsi, rdx
0x180118166  xor     ebp, ebp
0x180118168  mov     [rax+18h], rbp
0x18011816c  mov     [rax+20h], rbp
0x180118170  mov     r8, rdx; ppstm
0x180118173  lea     edx, [rbp+1]; fDeleteOnRelease
0x180118176  xor     ecx, ecx; hGlobal
0x180118178  call    cs:__imp_CreateStreamOnHGlobal
0x18011817f  nop     dword ptr [rax+rax+00h]
0x180118184  mov     ebx, eax
0x180118186  test    eax, eax
0x180118188  jns     short loc_18011818F
0x18011818a  lea     edx, [rbp+31h]
0x18011818d  jmp     short loc_1801181D7
0x18011818f  call    cs:__imp_RtlIsStateSeparationEnabled
0x180118196  nop     dword ptr [rax+rax+00h]
0x18011819b  lea     r14, aXmlVersion10En_4; "<?xml version=\"1.0\" encoding=\"utf-16"...
0x1801181a2  lea     rdi, aXmlVersion10En_25; "<?xml version=\"1.0\" encoding=\"utf-16"...
0x1801181a9  mov     rdx, rdi
0x1801181ac  test    al, al
0x1801181ae  cmovz   rdx, r14; unsigned __int64
0x1801181b2  or      rcx, 0FFFFFFFFFFFFFFFFh
0x1801181b6  inc     rcx
0x1801181b9  cmp     [rdx+rcx*2], bp
0x1801181bd  jnz     short loc_1801181B6
0x1801181bf  inc     rcx; unsigned __int64
0x1801181c2  lea     r8, [rsp+38h+cbInit]; unsigned __int64 *
0x1801181c7  call    ?ULongLongMult@@YAJ_K0PEA_K@Z; ULongLongMult(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x1801181cc  mov     ebx, eax
0x1801181ce  test    eax, eax
0x1801181d0  jns     short loc_1801181ED
0x1801181d2  mov     edx, 32h ; '2'; void *
0x1801181d7  mov     rcx, [rsp+38h]; this
0x1801181dc  mov     r9d, eax; char *
0x1801181df  lea     r8, aOnecoreuapAdmi_17; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x1801181e6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801181eb  jmp     short loc_18011823B
0x1801181ed  call    cs:__imp_RtlIsStateSeparationEnabled
0x1801181f4  nop     dword ptr [rax+rax+00h]
0x1801181f9  test    al, al
0x1801181fb  cmovz   rdi, r14
0x1801181ff  mov     edx, dword ptr [rsp+38h+cbInit]; cbInit
0x180118203  mov     rcx, rdi; pInit
0x180118206  call    cs:__imp_SHCreateMemStream
0x18011820d  nop     dword ptr [rax+rax+00h]
0x180118212  mov     rdx, rax
0x180118215  lea     rcx, [rsp+38h+arg_10]
0x18011821a  call    ??4?$ComPtr@UIStream@@@WRL@Microsoft@@QEAAAEAV012@PEAUIStream@@@Z; Microsoft::WRL::ComPtr<IStream>::operator=(IStream *)
0x18011821f  mov     rdx, [rsi]; struct IStream *
0x180118222  mov     rcx, [rsp+38h+arg_10]; struct IStream *
0x180118227  call    ?CreateDiagnosticData@@YAJPEAUIStream@@0@Z; CreateDiagnosticData(IStream *,IStream *)
0x18011822c  mov     ebx, eax
0x18011822e  test    eax, eax
0x180118230  jns     short loc_180118239
0x180118232  mov     edx, 37h ; '7'
0x180118237  jmp     short loc_1801181D7
0x180118239  mov     ebx, ebp
0x18011823b  lea     rcx, [rsp+38h+arg_10]
0x180118240  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x180118245  mov     eax, ebx
0x180118247  mov     rbx, [rsp+38h+arg_0]
0x18011824c  mov     rbp, [rsp+38h+arg_8]
0x180118251  add     rsp, 20h
0x180118255  pop     r14
0x180118257  pop     rdi
0x180118258  pop     rsi
0x180118259  retn
```
