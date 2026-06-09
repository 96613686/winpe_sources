# Microsoft::Windows::Mdm::MdmDiagnosticSource::DmAccountDiagDataSource::GetDiagnosticData(IStream * *)

- ea: `0x180105820`
- end: `0x18010592b`
- name: `?GetDiagnosticData@DmAccountDiagDataSource@MdmDiagnosticSource@Mdm@Windows@Microsoft@@UEAAJPEAPEAUIStream@@@Z`
- size: `267`
- prototype: `int(Microsoft::Windows::Mdm::MdmDiagnosticSource::DmAccountDiagDataSource *__hidden this, struct IStream **)`
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x1800eb1ac`
- `0x1800ed46c`
- `0x1800f8e70`
- `0x1800f962c`
- `0x180105820`
- `0x180123aa8`

## import_xrefs

- `ntdll!RtlIsStateSeparationEnabled` at `0x18010585f`
- `ntdll!RtlIsStateSeparationEnabled` at `0x1801058bd`
- `ntdll!RtlIsStateSeparationEnabled` at `0x18010585f`
- `ntdll!RtlIsStateSeparationEnabled` at `0x1801058bd`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x180105848`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x180105848`
- `api-ms-win-shcore-stream-l1-1-0!SHCreateMemStream` at `0x1801058d6`
- `api-ms-win-shcore-stream-l1-1-0!SHCreateMemStream` at `0x1801058d6`

## string_xrefs

- `0x18010586b`: `<?xml version="1.0" encoding="utf-16"?>\n<DiagData>\n  <DataSource name="DeviceManagementAccount">\n    <Key>\n      <Category>Enrollment</Category>\n      <Path>HKLM\Software\Microsoft\Provisioning\OMADM\Accounts\*</Path>\n      <Representation>EnrollmentId</Representation>\n      <Value>\n        <Name>AcctUId</Name>\n        <ValueRepresentation>AccountUID</ValueRepresentation>\n      </Value>\n      <Value>\n        <Name>Flags</Name>\n        <ValueRepresentation>Flags</ValueRepresentation>`
- `0x180105872`: `<?xml version="1.0" encoding="utf-16"?>\n<DiagData>\n  <DataSource name="OSDataDeviceManagementAccount">\n    <Key>\n      <Category>Enrollment</Category>\n      <Path>HKLM\OSData\Software\Microsoft\Provisioning\OMADM\Accounts\*</Path>\n      <Representation>EnrollmentId</Representation>\n      <Value>\n        <Name>AcctUId</Name>\n        <ValueRepresentation>AccountUID</ValueRepresentation>\n      </Value>\n      <Value>\n        <Name>Flags</Name>\n        <ValueRepresentation>Flags</ValueRe`
- `0x1801058af`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\dll\dmaccountdiagdata.cpp`

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
0x180105820  mov     rax, rsp
0x180105823  mov     [rax+8], rbx
0x180105827  mov     [rax+10h], rbp
0x18010582b  push    rsi
0x18010582c  push    rdi
0x18010582d  push    r14; int
0x18010582f  sub     rsp, 20h
0x180105833  mov     rsi, rdx
0x180105836  xor     ebp, ebp
0x180105838  mov     [rax+18h], rbp
0x18010583c  mov     [rax+20h], rbp
0x180105840  mov     r8, rdx; ppstm
0x180105843  lea     edx, [rbp+1]; fDeleteOnRelease
0x180105846  xor     ecx, ecx; hGlobal
0x180105848  call    cs:__imp_CreateStreamOnHGlobal
0x18010584f  nop     dword ptr [rax+rax+00h]
0x180105854  mov     ebx, eax
0x180105856  test    eax, eax
0x180105858  jns     short loc_18010585F
0x18010585a  lea     edx, [rbp+31h]
0x18010585d  jmp     short loc_1801058A7
0x18010585f  call    cs:__imp_RtlIsStateSeparationEnabled
0x180105866  nop     dword ptr [rax+rax+00h]
0x18010586b  lea     r14, aXmlVersion10En_23; "<?xml version=\"1.0\" encoding=\"utf-16"...
0x180105872  lea     rdi, aXmlVersion10En_16; "<?xml version=\"1.0\" encoding=\"utf-16"...
0x180105879  mov     rdx, rdi
0x18010587c  test    al, al
0x18010587e  cmovz   rdx, r14; unsigned __int64
0x180105882  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180105886  inc     rcx
0x180105889  cmp     [rdx+rcx*2], bp
0x18010588d  jnz     short loc_180105886
0x18010588f  inc     rcx; unsigned __int64
0x180105892  lea     r8, [rsp+38h+cbInit]; unsigned __int64 *
0x180105897  call    ?ULongLongMult@@YAJ_K0PEA_K@Z; ULongLongMult(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x18010589c  mov     ebx, eax
0x18010589e  test    eax, eax
0x1801058a0  jns     short loc_1801058BD
0x1801058a2  mov     edx, 32h ; '2'; void *
0x1801058a7  mov     rcx, [rsp+38h]; this
0x1801058ac  mov     r9d, eax; char *
0x1801058af  lea     r8, aOnecoreuapAdmi_34; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x1801058b6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801058bb  jmp     short loc_18010590B
0x1801058bd  call    cs:__imp_RtlIsStateSeparationEnabled
0x1801058c4  nop     dword ptr [rax+rax+00h]
0x1801058c9  test    al, al
0x1801058cb  cmovz   rdi, r14
0x1801058cf  mov     edx, dword ptr [rsp+38h+cbInit]; cbInit
0x1801058d3  mov     rcx, rdi; pInit
0x1801058d6  call    cs:__imp_SHCreateMemStream
0x1801058dd  nop     dword ptr [rax+rax+00h]
0x1801058e2  mov     rdx, rax
0x1801058e5  lea     rcx, [rsp+38h+arg_10]
0x1801058ea  call    ??4?$ComPtr@UIStream@@@WRL@Microsoft@@QEAAAEAV012@PEAUIStream@@@Z; Microsoft::WRL::ComPtr<IStream>::operator=(IStream *)
0x1801058ef  mov     rdx, [rsi]; struct IStream *
0x1801058f2  mov     rcx, [rsp+38h+arg_10]; struct IStream *
0x1801058f7  call    ?CreateDiagnosticData@@YAJPEAUIStream@@0@Z; CreateDiagnosticData(IStream *,IStream *)
0x1801058fc  mov     ebx, eax
0x1801058fe  test    eax, eax
0x180105900  jns     short loc_180105909
0x180105902  mov     edx, 37h ; '7'
0x180105907  jmp     short loc_1801058A7
0x180105909  mov     ebx, ebp
0x18010590b  lea     rcx, [rsp+38h+arg_10]
0x180105910  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x180105915  mov     eax, ebx
0x180105917  mov     rbx, [rsp+38h+arg_0]
0x18010591c  mov     rbp, [rsp+38h+arg_8]
0x180105921  add     rsp, 20h
0x180105925  pop     r14
0x180105927  pop     rdi
0x180105928  pop     rsi
0x180105929  retn
```
