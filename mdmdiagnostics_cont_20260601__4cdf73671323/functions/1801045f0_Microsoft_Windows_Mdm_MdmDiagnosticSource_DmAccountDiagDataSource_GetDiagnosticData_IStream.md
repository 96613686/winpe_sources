# Microsoft::Windows::Mdm::MdmDiagnosticSource::DmAccountDiagDataSource::GetDiagnosticData(IStream * *)

- ea: `0x1801045f0`
- end: `0x1801046e2`
- name: `?GetDiagnosticData@DmAccountDiagDataSource@MdmDiagnosticSource@Mdm@Windows@Microsoft@@UEAAJPEAPEAUIStream@@@Z`
- size: `242`
- prototype: `int(Microsoft::Windows::Mdm::MdmDiagnosticSource::DmAccountDiagDataSource *__hidden this, struct IStream **)`
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x1800ead14`
- `0x1800ece5c`
- `0x1800f7f10`
- `0x1800f8680`
- `0x1801045f0`
- `0x180122018`

## import_xrefs

- `ntdll!RtlIsStateSeparationEnabled` at `0x180104629`
- `ntdll!RtlIsStateSeparationEnabled` at `0x180104681`
- `ntdll!RtlIsStateSeparationEnabled` at `0x180104629`
- `ntdll!RtlIsStateSeparationEnabled` at `0x180104681`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x180104618`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x180104618`
- `api-ms-win-shcore-stream-l1-1-0!SHCreateMemStream` at `0x180104694`
- `api-ms-win-shcore-stream-l1-1-0!SHCreateMemStream` at `0x180104694`

## string_xrefs

- `0x180104636`: `<?xml version="1.0" encoding="utf-16"?>\n<DiagData>\n  <DataSource name="OSDataDeviceManagementAccount">\n    <Key>\n      <Category>Enrollment</Category>\n      <Path>HKLM\OSData\Software\Microsoft\Provisioning\OMADM\Accounts\*</Path>\n      <Representation>EnrollmentId</Representation>\n      <Value>\n        <Name>AcctUId</Name>\n        <ValueRepresentation>AccountUID</ValueRepresentation>\n      </Value>\n      <Value>\n        <Name>Flags</Name>\n        <ValueRepresentation>Flags</ValueRe`
- `0x18010462f`: `<?xml version="1.0" encoding="utf-16"?>\n<DiagData>\n  <DataSource name="DeviceManagementAccount">\n    <Key>\n      <Category>Enrollment</Category>\n      <Path>HKLM\Software\Microsoft\Provisioning\OMADM\Accounts\*</Path>\n      <Representation>EnrollmentId</Representation>\n      <Value>\n        <Name>AcctUId</Name>\n        <ValueRepresentation>AccountUID</ValueRepresentation>\n      </Value>\n      <Value>\n        <Name>Flags</Name>\n        <ValueRepresentation>Flags</ValueRepresentation>`
- `0x180104673`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\dll\dmaccountdiagdata.cpp`

## pseudocode

```c
__int64 __fastcall Microsoft::Windows::Mdm::MdmDiagnosticSource::DmAccountDiagDataSource::GetDiagnosticData(
        Microsoft::Windows::Mdm::MdmDiagnosticSource::DmAccountDiagDataSource *this,
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
    v7 = (const BYTE *)aXmlVersion10En_16;
    v8 = aXmlVersion10En_16;
    if ( !IsStateSeparationEnabled )
      v8 = (const wchar_t *)aXmlVersion10En_23;
    v9 = -1;
    do
      ++v9;
    while ( v8[v9] );
    StreamOnHGlobal = ULongLongMult(v9 + 1, (unsigned __int64)v8, &cbInit);
    v4 = StreamOnHGlobal;
    if ( StreamOnHGlobal >= 0 )
    {
      if ( !(unsigned __int8)RtlIsStateSeparationEnabled() )
        v7 = aXmlVersion10En_23;
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
    (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmdiagnostics\\dll\\dmaccountdiagdata.cpp",
    (const char *)(unsigned int)StreamOnHGlobal,
    v12);
LABEL_15:
  Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&v14);
  return v4;
}

```

## disassembly

```asm
0x1801045f0  mov     rax, rsp
0x1801045f3  mov     [rax+8], rbx
0x1801045f7  mov     [rax+10h], rbp
0x1801045fb  push    rsi
0x1801045fc  push    rdi
0x1801045fd  push    r14; int
0x1801045ff  sub     rsp, 20h
0x180104603  mov     rsi, rdx
0x180104606  xor     ebp, ebp
0x180104608  mov     [rax+18h], rbp
0x18010460c  mov     [rax+20h], rbp
0x180104610  mov     r8, rdx; ppstm
0x180104613  lea     edx, [rbp+1]; fDeleteOnRelease
0x180104616  xor     ecx, ecx; hGlobal
0x180104618  call    cs:__imp_CreateStreamOnHGlobal
0x18010461e  mov     ebx, eax
0x180104620  test    eax, eax
0x180104622  jns     short loc_180104629
0x180104624  lea     edx, [rbp+31h]
0x180104627  jmp     short loc_18010466B
0x180104629  call    cs:__imp_RtlIsStateSeparationEnabled
0x18010462f  lea     r14, aXmlVersion10En_23; "<?xml version=\"1.0\" encoding=\"utf-16"...
0x180104636  lea     rdi, aXmlVersion10En_16; "<?xml version=\"1.0\" encoding=\"utf-16"...
0x18010463d  mov     rdx, rdi
0x180104640  test    al, al
0x180104642  cmovz   rdx, r14; unsigned __int64
0x180104646  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18010464a  inc     rcx
0x18010464d  cmp     [rdx+rcx*2], bp
0x180104651  jnz     short loc_18010464A
0x180104653  inc     rcx; unsigned __int64
0x180104656  lea     r8, [rsp+38h+cbInit]; unsigned __int64 *
0x18010465b  call    ?ULongLongMult@@YAJ_K0PEA_K@Z; ULongLongMult(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x180104660  mov     ebx, eax
0x180104662  test    eax, eax
0x180104664  jns     short loc_180104681
0x180104666  mov     edx, 32h ; '2'; void *
0x18010466b  mov     rcx, [rsp+38h]; this
0x180104670  mov     r9d, eax; char *
0x180104673  lea     r8, aOnecoreuapAdmi_34; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x18010467a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18010467f  jmp     short loc_1801046C3
0x180104681  call    cs:__imp_RtlIsStateSeparationEnabled
0x180104687  test    al, al
0x180104689  cmovz   rdi, r14
0x18010468d  mov     edx, dword ptr [rsp+38h+cbInit]; cbInit
0x180104691  mov     rcx, rdi; pInit
0x180104694  call    cs:__imp_SHCreateMemStream
0x18010469a  mov     rdx, rax
0x18010469d  lea     rcx, [rsp+38h+arg_10]
0x1801046a2  call    ??4?$ComPtr@UIStream@@@WRL@Microsoft@@QEAAAEAV012@PEAUIStream@@@Z; Microsoft::WRL::ComPtr<IStream>::operator=(IStream *)
0x1801046a7  mov     rdx, [rsi]; struct IStream *
0x1801046aa  mov     rcx, [rsp+38h+arg_10]; struct IStream *
0x1801046af  call    ?CreateDiagnosticData@@YAJPEAUIStream@@0@Z; CreateDiagnosticData(IStream *,IStream *)
0x1801046b4  mov     ebx, eax
0x1801046b6  test    eax, eax
0x1801046b8  jns     short loc_1801046C1
0x1801046ba  mov     edx, 37h ; '7'
0x1801046bf  jmp     short loc_18010466B
0x1801046c1  mov     ebx, ebp
0x1801046c3  lea     rcx, [rsp+38h+arg_10]
0x1801046c8  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x1801046cd  mov     eax, ebx
0x1801046cf  mov     rbx, [rsp+38h+arg_0]
0x1801046d4  mov     rbp, [rsp+38h+arg_8]
0x1801046d9  add     rsp, 20h
0x1801046dd  pop     r14
0x1801046df  pop     rdi
0x1801046e0  pop     rsi
0x1801046e1  retn
```
