# Microsoft::Windows::Mdm::MdmDiagnosticSource::ResourceDiagDataSource::GetDiagnosticData(IStream * *)

- ea: `0x180117ff0`
- end: `0x1801180fb`
- name: `?GetDiagnosticData@ResourceDiagDataSource@MdmDiagnosticSource@Mdm@Windows@Microsoft@@UEAAJPEAPEAUIStream@@@Z`
- size: `267`
- prototype: `int(Microsoft::Windows::Mdm::MdmDiagnosticSource::ResourceDiagDataSource *__hidden this, struct IStream **)`
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x1800eb1ac`
- `0x1800ed46c`
- `0x1800f8e70`
- `0x1800f962c`
- `0x180117ff0`
- `0x180123aa8`

## import_xrefs

- `ntdll!RtlIsStateSeparationEnabled` at `0x18011802f`
- `ntdll!RtlIsStateSeparationEnabled` at `0x18011808d`
- `ntdll!RtlIsStateSeparationEnabled` at `0x18011802f`
- `ntdll!RtlIsStateSeparationEnabled` at `0x18011808d`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x180118018`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x180118018`
- `api-ms-win-shcore-stream-l1-1-0!SHCreateMemStream` at `0x1801180a6`
- `api-ms-win-shcore-stream-l1-1-0!SHCreateMemStream` at `0x1801180a6`

## string_xrefs

- `0x18011803b`: `<?xml version="1.0" encoding="utf-16"?>\n<DiagData>\n  <DataSource name="Resources">\n    <Key>\n      <Category>Enrollment</Category>\n      <Path>HKLM\Software\Microsoft\EnterpriseResourceManager\Tracked\*</Path>\n      <Representation>EnrollmentID</Representation>\n      <Key>\n        <Category>Scope</Category>\n        <Path>*</Path>\n        <Representation>ResourceTarget</Representation>\n        <Key>\n          <Category>Resources</Category>\n          <Path>default</Path>\n          <R`
- `0x180118042`: `<?xml version="1.0" encoding="utf-16"?>\n<DiagData>\n  <DataSource name="OSDataResources">\n    <Key>\n      <Category>Enrollment</Category>\n      <Path>HKLM\OSData\Software\Microsoft\EnterpriseResourceManager\Tracked\*</Path>\n      <Representation>EnrollmentID</Representation>\n      <Key>\n        <Category>Scope</Category>\n        <Path>*</Path>\n        <Representation>ResourceTarget</Representation>\n        <Key>\n          <Category>Resources</Category>\n          <Path>default</Path>\`
- `0x18011807f`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\dll\resourcediagdata.cpp`

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
0x180117ff0  mov     rax, rsp
0x180117ff3  mov     [rax+8], rbx
0x180117ff7  mov     [rax+10h], rbp
0x180117ffb  push    rsi
0x180117ffc  push    rdi
0x180117ffd  push    r14; int
0x180117fff  sub     rsp, 20h
0x180118003  mov     rsi, rdx
0x180118006  xor     ebp, ebp
0x180118008  mov     [rax+18h], rbp
0x18011800c  mov     [rax+20h], rbp
0x180118010  mov     r8, rdx; ppstm
0x180118013  lea     edx, [rbp+1]; fDeleteOnRelease
0x180118016  xor     ecx, ecx; hGlobal
0x180118018  call    cs:__imp_CreateStreamOnHGlobal
0x18011801f  nop     dword ptr [rax+rax+00h]
0x180118024  mov     ebx, eax
0x180118026  test    eax, eax
0x180118028  jns     short loc_18011802F
0x18011802a  lea     edx, [rbp+31h]
0x18011802d  jmp     short loc_180118077
0x18011802f  call    cs:__imp_RtlIsStateSeparationEnabled
0x180118036  nop     dword ptr [rax+rax+00h]
0x18011803b  lea     r14, aXmlVersion10En_7; "<?xml version=\"1.0\" encoding=\"utf-16"...
0x180118042  lea     rdi, aXmlVersion10En_26; "<?xml version=\"1.0\" encoding=\"utf-16"...
0x180118049  mov     rdx, rdi
0x18011804c  test    al, al
0x18011804e  cmovz   rdx, r14; unsigned __int64
0x180118052  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180118056  inc     rcx
0x180118059  cmp     [rdx+rcx*2], bp
0x18011805d  jnz     short loc_180118056
0x18011805f  inc     rcx; unsigned __int64
0x180118062  lea     r8, [rsp+38h+cbInit]; unsigned __int64 *
0x180118067  call    ?ULongLongMult@@YAJ_K0PEA_K@Z; ULongLongMult(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x18011806c  mov     ebx, eax
0x18011806e  test    eax, eax
0x180118070  jns     short loc_18011808D
0x180118072  mov     edx, 32h ; '2'; void *
0x180118077  mov     rcx, [rsp+38h]; this
0x18011807c  mov     r9d, eax; char *
0x18011807f  lea     r8, aOnecoreuapAdmi_37; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x180118086  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18011808b  jmp     short loc_1801180DB
0x18011808d  call    cs:__imp_RtlIsStateSeparationEnabled
0x180118094  nop     dword ptr [rax+rax+00h]
0x180118099  test    al, al
0x18011809b  cmovz   rdi, r14
0x18011809f  mov     edx, dword ptr [rsp+38h+cbInit]; cbInit
0x1801180a3  mov     rcx, rdi; pInit
0x1801180a6  call    cs:__imp_SHCreateMemStream
0x1801180ad  nop     dword ptr [rax+rax+00h]
0x1801180b2  mov     rdx, rax
0x1801180b5  lea     rcx, [rsp+38h+arg_10]
0x1801180ba  call    ??4?$ComPtr@UIStream@@@WRL@Microsoft@@QEAAAEAV012@PEAUIStream@@@Z; Microsoft::WRL::ComPtr<IStream>::operator=(IStream *)
0x1801180bf  mov     rdx, [rsi]; struct IStream *
0x1801180c2  mov     rcx, [rsp+38h+arg_10]; struct IStream *
0x1801180c7  call    ?CreateDiagnosticData@@YAJPEAUIStream@@0@Z; CreateDiagnosticData(IStream *,IStream *)
0x1801180cc  mov     ebx, eax
0x1801180ce  test    eax, eax
0x1801180d0  jns     short loc_1801180D9
0x1801180d2  mov     edx, 37h ; '7'
0x1801180d7  jmp     short loc_180118077
0x1801180d9  mov     ebx, ebp
0x1801180db  lea     rcx, [rsp+38h+arg_10]
0x1801180e0  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x1801180e5  mov     eax, ebx
0x1801180e7  mov     rbx, [rsp+38h+arg_0]
0x1801180ec  mov     rbp, [rsp+38h+arg_8]
0x1801180f1  add     rsp, 20h
0x1801180f5  pop     r14
0x1801180f7  pop     rdi
0x1801180f8  pop     rsi
0x1801180f9  retn
```
