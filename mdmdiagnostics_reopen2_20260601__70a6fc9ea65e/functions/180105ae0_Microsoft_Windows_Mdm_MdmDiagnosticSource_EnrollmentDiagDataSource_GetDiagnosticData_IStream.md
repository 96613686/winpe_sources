# Microsoft::Windows::Mdm::MdmDiagnosticSource::EnrollmentDiagDataSource::GetDiagnosticData(IStream * *)

- ea: `0x180105ae0`
- end: `0x180105beb`
- name: `?GetDiagnosticData@EnrollmentDiagDataSource@MdmDiagnosticSource@Mdm@Windows@Microsoft@@UEAAJPEAPEAUIStream@@@Z`
- size: `267`
- prototype: `int(Microsoft::Windows::Mdm::MdmDiagnosticSource::EnrollmentDiagDataSource *__hidden this, struct IStream **)`
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x1800eb1ac`
- `0x1800ed46c`
- `0x1800f8e70`
- `0x1800f962c`
- `0x180105ae0`
- `0x180123aa8`

## import_xrefs

- `ntdll!RtlIsStateSeparationEnabled` at `0x180105b1f`
- `ntdll!RtlIsStateSeparationEnabled` at `0x180105b7d`
- `ntdll!RtlIsStateSeparationEnabled` at `0x180105b1f`
- `ntdll!RtlIsStateSeparationEnabled` at `0x180105b7d`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x180105b08`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x180105b08`
- `api-ms-win-shcore-stream-l1-1-0!SHCreateMemStream` at `0x180105b96`
- `api-ms-win-shcore-stream-l1-1-0!SHCreateMemStream` at `0x180105b96`

## string_xrefs

- `0x180105b32`: `<?xml version="1.0" encoding="utf-16"?>\n<DiagData>\n  <DataSource name="OSDataEnrollments">\n    <Key>\n      <Category>Enrollment</Category>\n      <Path>HKLM\OSData\Software\Microsoft\Enrollments\*</Path>\n      <Representation>EnrollmentId</Representation>\n      <Value>\n        <Name>Altitude</Name>\n        <ValueRepresentation>Altitude</ValueRepresentation>\n      </Value>\n      <Value>\n        <Name>EnrollmentState</Name>\n        <ValueRepresentation>EnrollmentState</ValueRepresentat`
- `0x180105b2b`: `<?xml version="1.0" encoding="utf-16"?>\n<DiagData>\n  <DataSource name="Enrollments">\n    <Key>\n      <Category>Enrollment</Category>\n      <Path>HKLM\Software\Microsoft\Enrollments\*</Path>\n      <Representation>EnrollmentId</Representation>\n      <Value>\n        <Name>Altitude</Name>\n        <ValueRepresentation>Altitude</ValueRepresentation>\n      </Value>\n      <Value>\n        <Name>EnrollmentState</Name>\n        <ValueRepresentation>EnrollmentState</ValueRepresentation>\n      <`
- `0x180105b6f`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\dll\enrollmentdiagdata.cpp`

## pseudocode

```c
__int64 __fastcall Microsoft::Windows::Mdm::MdmDiagnosticSource::EnrollmentDiagDataSource::GetDiagnosticData(
        Microsoft::Windows::Mdm::MdmDiagnosticSource::EnrollmentDiagDataSource *this,
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
    v7 = (const BYTE *)aXmlVersion10En_5;
    v8 = aXmlVersion10En_5;
    if ( !IsStateSeparationEnabled )
      v8 = (const wchar_t *)aXmlVersion10En_21;
    v9 = -1;
    do
      ++v9;
    while ( v8[v9] );
    StreamOnHGlobal = ULongLongMult(v9 + 1, (unsigned __int64)v8, &cbInit);
    v4 = StreamOnHGlobal;
    if ( StreamOnHGlobal >= 0 )
    {
      if ( !(unsigned __int8)RtlIsStateSeparationEnabled() )
        v7 = aXmlVersion10En_21;
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
    (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmdiagnostics\\dll\\enrollmentdiagdata.cpp",
    (const char *)(unsigned int)StreamOnHGlobal,
    v12);
LABEL_15:
  Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&v14);
  return v4;
}

```

## disassembly

```asm
0x180105ae0  mov     rax, rsp
0x180105ae3  mov     [rax+8], rbx
0x180105ae7  mov     [rax+10h], rbp
0x180105aeb  push    rsi
0x180105aec  push    rdi
0x180105aed  push    r14; int
0x180105aef  sub     rsp, 20h
0x180105af3  mov     rsi, rdx
0x180105af6  xor     ebp, ebp
0x180105af8  mov     [rax+18h], rbp
0x180105afc  mov     [rax+20h], rbp
0x180105b00  mov     r8, rdx; ppstm
0x180105b03  lea     edx, [rbp+1]; fDeleteOnRelease
0x180105b06  xor     ecx, ecx; hGlobal
0x180105b08  call    cs:__imp_CreateStreamOnHGlobal
0x180105b0f  nop     dword ptr [rax+rax+00h]
0x180105b14  mov     ebx, eax
0x180105b16  test    eax, eax
0x180105b18  jns     short loc_180105B1F
0x180105b1a  lea     edx, [rbp+31h]
0x180105b1d  jmp     short loc_180105B67
0x180105b1f  call    cs:__imp_RtlIsStateSeparationEnabled
0x180105b26  nop     dword ptr [rax+rax+00h]
0x180105b2b  lea     r14, aXmlVersion10En_21; "<?xml version=\"1.0\" encoding=\"utf-16"...
0x180105b32  lea     rdi, aXmlVersion10En_5; "<?xml version=\"1.0\" encoding=\"utf-16"...
0x180105b39  mov     rdx, rdi
0x180105b3c  test    al, al
0x180105b3e  cmovz   rdx, r14; unsigned __int64
0x180105b42  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180105b46  inc     rcx
0x180105b49  cmp     [rdx+rcx*2], bp
0x180105b4d  jnz     short loc_180105B46
0x180105b4f  inc     rcx; unsigned __int64
0x180105b52  lea     r8, [rsp+38h+cbInit]; unsigned __int64 *
0x180105b57  call    ?ULongLongMult@@YAJ_K0PEA_K@Z; ULongLongMult(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x180105b5c  mov     ebx, eax
0x180105b5e  test    eax, eax
0x180105b60  jns     short loc_180105B7D
0x180105b62  mov     edx, 32h ; '2'; void *
0x180105b67  mov     rcx, [rsp+38h]; this
0x180105b6c  mov     r9d, eax; char *
0x180105b6f  lea     r8, aOnecoreuapAdmi_7; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x180105b76  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180105b7b  jmp     short loc_180105BCB
0x180105b7d  call    cs:__imp_RtlIsStateSeparationEnabled
0x180105b84  nop     dword ptr [rax+rax+00h]
0x180105b89  test    al, al
0x180105b8b  cmovz   rdi, r14
0x180105b8f  mov     edx, dword ptr [rsp+38h+cbInit]; cbInit
0x180105b93  mov     rcx, rdi; pInit
0x180105b96  call    cs:__imp_SHCreateMemStream
0x180105b9d  nop     dword ptr [rax+rax+00h]
0x180105ba2  mov     rdx, rax
0x180105ba5  lea     rcx, [rsp+38h+arg_10]
0x180105baa  call    ??4?$ComPtr@UIStream@@@WRL@Microsoft@@QEAAAEAV012@PEAUIStream@@@Z; Microsoft::WRL::ComPtr<IStream>::operator=(IStream *)
0x180105baf  mov     rdx, [rsi]; struct IStream *
0x180105bb2  mov     rcx, [rsp+38h+arg_10]; struct IStream *
0x180105bb7  call    ?CreateDiagnosticData@@YAJPEAUIStream@@0@Z; CreateDiagnosticData(IStream *,IStream *)
0x180105bbc  mov     ebx, eax
0x180105bbe  test    eax, eax
0x180105bc0  jns     short loc_180105BC9
0x180105bc2  mov     edx, 37h ; '7'
0x180105bc7  jmp     short loc_180105B67
0x180105bc9  mov     ebx, ebp
0x180105bcb  lea     rcx, [rsp+38h+arg_10]
0x180105bd0  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x180105bd5  mov     eax, ebx
0x180105bd7  mov     rbx, [rsp+38h+arg_0]
0x180105bdc  mov     rbp, [rsp+38h+arg_8]
0x180105be1  add     rsp, 20h
0x180105be5  pop     r14
0x180105be7  pop     rdi
0x180105be8  pop     rsi
0x180105be9  retn
```
