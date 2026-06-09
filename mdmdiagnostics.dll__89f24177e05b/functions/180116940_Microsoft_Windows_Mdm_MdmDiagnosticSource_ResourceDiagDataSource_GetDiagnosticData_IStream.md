# Microsoft::Windows::Mdm::MdmDiagnosticSource::ResourceDiagDataSource::GetDiagnosticData(IStream * *)

- ea: `0x180116940`
- end: `0x180116a32`
- name: `?GetDiagnosticData@ResourceDiagDataSource@MdmDiagnosticSource@Mdm@Windows@Microsoft@@UEAAJPEAPEAUIStream@@@Z`
- size: `242`
- prototype: `int(Microsoft::Windows::Mdm::MdmDiagnosticSource::ResourceDiagDataSource *__hidden this, struct IStream **)`
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x1800ead14`
- `0x1800ece5c`
- `0x1800f7f10`
- `0x1800f8680`
- `0x180116940`
- `0x180122018`

## import_xrefs

- `ntdll!RtlIsStateSeparationEnabled` at `0x180116979`
- `ntdll!RtlIsStateSeparationEnabled` at `0x1801169d1`
- `ntdll!RtlIsStateSeparationEnabled` at `0x180116979`
- `ntdll!RtlIsStateSeparationEnabled` at `0x1801169d1`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x180116968`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x180116968`
- `api-ms-win-shcore-stream-l1-1-0!SHCreateMemStream` at `0x1801169e4`
- `api-ms-win-shcore-stream-l1-1-0!SHCreateMemStream` at `0x1801169e4`

## string_xrefs

- `0x180116986`: `<?xml version="1.0" encoding="utf-16"?>\n<DiagData>\n  <DataSource name="OSDataResources">\n    <Key>\n      <Category>Enrollment</Category>\n      <Path>HKLM\OSData\Software\Microsoft\EnterpriseResourceManager\Tracked\*</Path>\n      <Representation>EnrollmentID</Representation>\n      <Key>\n        <Category>Scope</Category>\n        <Path>*</Path>\n        <Representation>ResourceTarget</Representation>\n        <Key>\n          <Category>Resources</Category>\n          <Path>default</Path>\`
- `0x18011697f`: `<?xml version="1.0" encoding="utf-16"?>\n<DiagData>\n  <DataSource name="Resources">\n    <Key>\n      <Category>Enrollment</Category>\n      <Path>HKLM\Software\Microsoft\EnterpriseResourceManager\Tracked\*</Path>\n      <Representation>EnrollmentID</Representation>\n      <Key>\n        <Category>Scope</Category>\n        <Path>*</Path>\n        <Representation>ResourceTarget</Representation>\n        <Key>\n          <Category>Resources</Category>\n          <Path>default</Path>\n          <R`
- `0x1801169c3`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\dll\resourcediagdata.cpp`

## pseudocode

```c
__int64 __fastcall Microsoft::Windows::Mdm::MdmDiagnosticSource::ResourceDiagDataSource::GetDiagnosticData(
        Microsoft::Windows::Mdm::MdmDiagnosticSource::ResourceDiagDataSource *this,
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
    v7 = (const BYTE *)L"<?xml version=\"1.0\" encoding=\"utf-16\"?>\n"
                        "<DiagData>\n"
                        "  <DataSource name=\"OSDataResources\">\n"
                        "    <Key>\n"
                        "      <Category>Enrollment</Category>\n"
                        "      <Path>HKLM\\OSData\\Software\\Microsoft\\EnterpriseResourceManager\\Tracked\\*</Path>\n"
                        "      <Representation>EnrollmentID</Representation>\n"
                        "      <Key>\n"
                        "        <Category>Scope</Category>\n"
                        "        <Path>*</Path>\n"
                        "        <Representation>ResourceTarget</Representation>\n"
                        "        <Key>\n"
                        "          <Category>Resources</Category>\n"
                        "          <Path>default</Path>\n"
                        "          <Representation>Type</Representation>\n"
                        "          <Value>\n"
                        "            <Name>*</Name>\n"
                        "            <ValueRepresentation>ResourceName</ValueRepresentation>\n"
                        "        </Value>\n"
                        "        </Key>\n"
                        "      </Key>\n"
                        "    </Key>\n"
                        "  </DataSource>\n"
                        "</DiagData>";
    v8 = L"<?xml version=\"1.0\" encoding=\"utf-16\"?>\n"
          "<DiagData>\n"
          "  <DataSource name=\"OSDataResources\">\n"
          "    <Key>\n"
          "      <Category>Enrollment</Category>\n"
          "      <Path>HKLM\\OSData\\Software\\Microsoft\\EnterpriseResourceManager\\Tracked\\*</Path>\n"
          "      <Representation>EnrollmentID</Representation>\n"
          "      <Key>\n"
          "        <Category>Scope</Category>\n"
          "        <Path>*</Path>\n"
          "        <Representation>ResourceTarget</Representation>\n"
          "        <Key>\n"
          "          <Category>Resources</Category>\n"
          "          <Path>default</Path>\n"
          "          <Representation>Type</Representation>\n"
          "          <Value>\n"
          "            <Name>*</Name>\n"
          "            <ValueRepresentation>ResourceName</ValueRepresentation>\n"
          "        </Value>\n"
          "        </Key>\n"
          "      </Key>\n"
          "    </Key>\n"
          "  </DataSource>\n"
          "</DiagData>";
    if ( !IsStateSeparationEnabled )
      v8 = (const wchar_t *)L"<?xml version=\"1.0\" encoding=\"utf-16\"?>\n"
                             "<DiagData>\n"
                             "  <DataSource name=\"Resources\">\n"
                             "    <Key>\n"
                             "      <Category>Enrollment</Category>\n"
                             "      <Path>HKLM\\Software\\Microsoft\\EnterpriseResourceManager\\Tracked\\*</Path>\n"
                             "      <Representation>EnrollmentID</Representation>\n"
                             "      <Key>\n"
                             "        <Category>Scope</Category>\n"
                             "        <Path>*</Path>\n"
                             "        <Representation>ResourceTarget</Representation>\n"
                             "        <Key>\n"
                             "          <Category>Resources</Category>\n"
                             "          <Path>default</Path>\n"
                             "          <Representation>Type</Representation>\n"
                             "          <Value>\n"
                             "            <Name>*</Name>\n"
                             "            <ValueRepresentation>ResourceName</ValueRepresentation>\n"
                             "        </Value>\n"
                             "        </Key>\n"
                             "      </Key>\n"
                             "    </Key>\n"
                             "  </DataSource>\n"
                             "</DiagData>";
    v9 = -1;
    do
      ++v9;
    while ( v8[v9] );
    StreamOnHGlobal = ULongLongMult(v9 + 1, (unsigned __int64)v8, &cbInit);
    v4 = StreamOnHGlobal;
    if ( StreamOnHGlobal >= 0 )
    {
      if ( !(unsigned __int8)RtlIsStateSeparationEnabled() )
        v7 = L"<?xml version=\"1.0\" encoding=\"utf-16\"?>\n"
              "<DiagData>\n"
              "  <DataSource name=\"Resources\">\n"
              "    <Key>\n"
              "      <Category>Enrollment</Category>\n"
              "      <Path>HKLM\\Software\\Microsoft\\EnterpriseResourceManager\\Tracked\\*</Path>\n"
              "      <Representation>EnrollmentID</Representation>\n"
              "      <Key>\n"
              "        <Category>Scope</Category>\n"
              "        <Path>*</Path>\n"
              "        <Representation>ResourceTarget</Representation>\n"
              "        <Key>\n"
              "          <Category>Resources</Category>\n"
              "          <Path>default</Path>\n"
              "          <Representation>Type</Representation>\n"
              "          <Value>\n"
              "            <Name>*</Name>\n"
              "            <ValueRepresentation>ResourceName</ValueRepresentation>\n"
              "        </Value>\n"
              "        </Key>\n"
              "      </Key>\n"
              "    </Key>\n"
              "  </DataSource>\n"
              "</DiagData>";
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
    (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmdiagnostics\\dll\\resourcediagdata.cpp",
    (const char *)(unsigned int)StreamOnHGlobal,
    v12);
LABEL_15:
  Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&v14);
  return v4;
}

```

## disassembly

```asm
0x180116940  mov     rax, rsp
0x180116943  mov     [rax+8], rbx
0x180116947  mov     [rax+10h], rbp
0x18011694b  push    rsi
0x18011694c  push    rdi
0x18011694d  push    r14; int
0x18011694f  sub     rsp, 20h
0x180116953  mov     rsi, rdx
0x180116956  xor     ebp, ebp
0x180116958  mov     [rax+18h], rbp
0x18011695c  mov     [rax+20h], rbp
0x180116960  mov     r8, rdx; ppstm
0x180116963  lea     edx, [rbp+1]; fDeleteOnRelease
0x180116966  xor     ecx, ecx; hGlobal
0x180116968  call    cs:__imp_CreateStreamOnHGlobal
0x18011696e  mov     ebx, eax
0x180116970  test    eax, eax
0x180116972  jns     short loc_180116979
0x180116974  lea     edx, [rbp+31h]
0x180116977  jmp     short loc_1801169BB
0x180116979  call    cs:__imp_RtlIsStateSeparationEnabled
0x18011697f  lea     r14, aXmlVersion10En_7; "<?xml version=\"1.0\" encoding=\"utf-16"...
0x180116986  lea     rdi, aXmlVersion10En_26; "<?xml version=\"1.0\" encoding=\"utf-16"...
0x18011698d  mov     rdx, rdi
0x180116990  test    al, al
0x180116992  cmovz   rdx, r14; unsigned __int64
0x180116996  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18011699a  inc     rcx
0x18011699d  cmp     [rdx+rcx*2], bp
0x1801169a1  jnz     short loc_18011699A
0x1801169a3  inc     rcx; unsigned __int64
0x1801169a6  lea     r8, [rsp+38h+cbInit]; unsigned __int64 *
0x1801169ab  call    ?ULongLongMult@@YAJ_K0PEA_K@Z; ULongLongMult(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x1801169b0  mov     ebx, eax
0x1801169b2  test    eax, eax
0x1801169b4  jns     short loc_1801169D1
0x1801169b6  mov     edx, 32h ; '2'; void *
0x1801169bb  mov     rcx, [rsp+38h]; this
0x1801169c0  mov     r9d, eax; char *
0x1801169c3  lea     r8, aOnecoreuapAdmi_37; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x1801169ca  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801169cf  jmp     short loc_180116A13
0x1801169d1  call    cs:__imp_RtlIsStateSeparationEnabled
0x1801169d7  test    al, al
0x1801169d9  cmovz   rdi, r14
0x1801169dd  mov     edx, dword ptr [rsp+38h+cbInit]; cbInit
0x1801169e1  mov     rcx, rdi; pInit
0x1801169e4  call    cs:__imp_SHCreateMemStream
0x1801169ea  mov     rdx, rax
0x1801169ed  lea     rcx, [rsp+38h+arg_10]
0x1801169f2  call    ??4?$ComPtr@UIStream@@@WRL@Microsoft@@QEAAAEAV012@PEAUIStream@@@Z; Microsoft::WRL::ComPtr<IStream>::operator=(IStream *)
0x1801169f7  mov     rdx, [rsi]; struct IStream *
0x1801169fa  mov     rcx, [rsp+38h+arg_10]; struct IStream *
0x1801169ff  call    ?CreateDiagnosticData@@YAJPEAUIStream@@0@Z; CreateDiagnosticData(IStream *,IStream *)
0x180116a04  mov     ebx, eax
0x180116a06  test    eax, eax
0x180116a08  jns     short loc_180116A11
0x180116a0a  mov     edx, 37h ; '7'
0x180116a0f  jmp     short loc_1801169BB
0x180116a11  mov     ebx, ebp
0x180116a13  lea     rcx, [rsp+38h+arg_10]
0x180116a18  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x180116a1d  mov     eax, ebx
0x180116a1f  mov     rbx, [rsp+38h+arg_0]
0x180116a24  mov     rbp, [rsp+38h+arg_8]
0x180116a29  add     rsp, 20h
0x180116a2d  pop     r14
0x180116a2f  pop     rdi
0x180116a30  pop     rsi
0x180116a31  retn
```
