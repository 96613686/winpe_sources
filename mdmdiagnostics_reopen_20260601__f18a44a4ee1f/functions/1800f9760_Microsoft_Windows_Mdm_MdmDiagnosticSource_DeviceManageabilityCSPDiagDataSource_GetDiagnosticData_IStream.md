# Microsoft::Windows::Mdm::MdmDiagnosticSource::DeviceManageabilityCSPDiagDataSource::GetDiagnosticData(IStream * *)

- ea: `0x1800f9760`
- end: `0x1800f986b`
- name: `?GetDiagnosticData@DeviceManageabilityCSPDiagDataSource@MdmDiagnosticSource@Mdm@Windows@Microsoft@@UEAAJPEAPEAUIStream@@@Z`
- size: `267`
- prototype: `int(Microsoft::Windows::Mdm::MdmDiagnosticSource::DeviceManageabilityCSPDiagDataSource *__hidden this, struct IStream **)`
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x1800eb1ac`
- `0x1800ed46c`
- `0x1800f8e70`
- `0x1800f962c`
- `0x1800f9760`
- `0x180123aa8`

## import_xrefs

- `ntdll!RtlIsStateSeparationEnabled` at `0x1800f979f`
- `ntdll!RtlIsStateSeparationEnabled` at `0x1800f97fd`
- `ntdll!RtlIsStateSeparationEnabled` at `0x1800f979f`
- `ntdll!RtlIsStateSeparationEnabled` at `0x1800f97fd`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x1800f9788`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x1800f9788`
- `api-ms-win-shcore-stream-l1-1-0!SHCreateMemStream` at `0x1800f9816`
- `api-ms-win-shcore-stream-l1-1-0!SHCreateMemStream` at `0x1800f9816`

## string_xrefs

- `0x1800f97ab`: `<?xml version="1.0" encoding="utf-16"?>\n<DiagData>\n  <DataSource name="DeviceManageabilityProviderInfo">\n    <Key>\n      <Category>Providers</Category>\n      <Path>HKLM\Software\Microsoft\DeviceManageabilityCSP\Provider</Path>\n      <Key>\n        <Category>Provider</Category>\n        <Path>*</Path>\n        <Representation>ProviderID</Representation>\n        <Value>\n          <Name>*</Name>\n          <ValueRepresentation>*</ValueRepresentation>\n        </Value>\n      </Key>\n    </K`
- `0x1800f97b2`: `<?xml version="1.0" encoding="utf-16"?>\n<DiagData>\n  <DataSource name="OSDataDeviceManageabilityProviderInfo">\n    <Key>\n      <Category>Providers</Category>\n      <Path>HKLM\OSData\Software\Microsoft\DeviceManageabilityCSP\Provider</Path>\n      <Key>\n        <Category>Provider</Category>\n        <Path>*</Path>\n        <Representation>ProviderID</Representation>\n        <Value>\n          <Name>*</Name>\n          <ValueRepresentation>*</ValueRepresentation>\n        </Value>\n      </`
- `0x1800f97ef`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\dll\devicemanageabilitycspdiagdata.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Microsoft::Windows::Mdm::MdmDiagnosticSource::DeviceManageabilityCSPDiagDataSource::GetDiagnosticData(
        Microsoft::Windows::Mdm::MdmDiagnosticSource::DeviceManageabilityCSPDiagDataSource *this,
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
                        "  <DataSource name=\"OSDataDeviceManageabilityProviderInfo\">\n"
                        "    <Key>\n"
                        "      <Category>Providers</Category>\n"
                        "      <Path>HKLM\\OSData\\Software\\Microsoft\\DeviceManageabilityCSP\\Provider</Path>\n"
                        "      <Key>\n"
                        "        <Category>Provider</Category>\n"
                        "        <Path>*</Path>\n"
                        "        <Representation>ProviderID</Representation>\n"
                        "        <Value>\n"
                        "          <Name>*</Name>\n"
                        "          <ValueRepresentation>*</ValueRepresentation>\n"
                        "        </Value>\n"
                        "      </Key>\n"
                        "    </Key>\n"
                        "  </DataSource>\n"
                        "</DiagData>";
    v8 = L"<?xml version=\"1.0\" encoding=\"utf-16\"?>\n"
          "<DiagData>\n"
          "  <DataSource name=\"OSDataDeviceManageabilityProviderInfo\">\n"
          "    <Key>\n"
          "      <Category>Providers</Category>\n"
          "      <Path>HKLM\\OSData\\Software\\Microsoft\\DeviceManageabilityCSP\\Provider</Path>\n"
          "      <Key>\n"
          "        <Category>Provider</Category>\n"
          "        <Path>*</Path>\n"
          "        <Representation>ProviderID</Representation>\n"
          "        <Value>\n"
          "          <Name>*</Name>\n"
          "          <ValueRepresentation>*</ValueRepresentation>\n"
          "        </Value>\n"
          "      </Key>\n"
          "    </Key>\n"
          "  </DataSource>\n"
          "</DiagData>";
    if ( !IsStateSeparationEnabled )
      v8 = (const wchar_t *)L"<?xml version=\"1.0\" encoding=\"utf-16\"?>\n"
                             "<DiagData>\n"
                             "  <DataSource name=\"DeviceManageabilityProviderInfo\">\n"
                             "    <Key>\n"
                             "      <Category>Providers</Category>\n"
                             "      <Path>HKLM\\Software\\Microsoft\\DeviceManageabilityCSP\\Provider</Path>\n"
                             "      <Key>\n"
                             "        <Category>Provider</Category>\n"
                             "        <Path>*</Path>\n"
                             "        <Representation>ProviderID</Representation>\n"
                             "        <Value>\n"
                             "          <Name>*</Name>\n"
                             "          <ValueRepresentation>*</ValueRepresentation>\n"
                             "        </Value>\n"
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
              "  <DataSource name=\"DeviceManageabilityProviderInfo\">\n"
              "    <Key>\n"
              "      <Category>Providers</Category>\n"
              "      <Path>HKLM\\Software\\Microsoft\\DeviceManageabilityCSP\\Provider</Path>\n"
              "      <Key>\n"
              "        <Category>Provider</Category>\n"
              "        <Path>*</Path>\n"
              "        <Representation>ProviderID</Representation>\n"
              "        <Value>\n"
              "          <Name>*</Name>\n"
              "          <ValueRepresentation>*</ValueRepresentation>\n"
              "        </Value>\n"
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
    (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmdiagnostics\\dll\\devicemanageabilitycspdiagdata.cpp",
    (const char *)(unsigned int)StreamOnHGlobal,
    v12);
LABEL_15:
  Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&v14);
  return v4;
}

```

## disassembly

```asm
0x1800f9760  mov     rax, rsp
0x1800f9763  mov     [rax+8], rbx
0x1800f9767  mov     [rax+10h], rbp
0x1800f976b  push    rsi
0x1800f976c  push    rdi
0x1800f976d  push    r14; int
0x1800f976f  sub     rsp, 20h
0x1800f9773  mov     rsi, rdx
0x1800f9776  xor     ebp, ebp
0x1800f9778  mov     [rax+18h], rbp
0x1800f977c  mov     [rax+20h], rbp
0x1800f9780  mov     r8, rdx; ppstm
0x1800f9783  lea     edx, [rbp+1]; fDeleteOnRelease
0x1800f9786  xor     ecx, ecx; hGlobal
0x1800f9788  call    cs:__imp_CreateStreamOnHGlobal
0x1800f978f  nop     dword ptr [rax+rax+00h]
0x1800f9794  mov     ebx, eax
0x1800f9796  test    eax, eax
0x1800f9798  jns     short loc_1800F979F
0x1800f979a  lea     edx, [rbp+31h]
0x1800f979d  jmp     short loc_1800F97E7
0x1800f979f  call    cs:__imp_RtlIsStateSeparationEnabled
0x1800f97a6  nop     dword ptr [rax+rax+00h]
0x1800f97ab  lea     r14, aXmlVersion10En; "<?xml version=\"1.0\" encoding=\"utf-16"...
0x1800f97b2  lea     rdi, aXmlVersion10En_20; "<?xml version=\"1.0\" encoding=\"utf-16"...
0x1800f97b9  mov     rdx, rdi
0x1800f97bc  test    al, al
0x1800f97be  cmovz   rdx, r14; unsigned __int64
0x1800f97c2  or      rcx, 0FFFFFFFFFFFFFFFFh
0x1800f97c6  inc     rcx
0x1800f97c9  cmp     [rdx+rcx*2], bp
0x1800f97cd  jnz     short loc_1800F97C6
0x1800f97cf  inc     rcx; unsigned __int64
0x1800f97d2  lea     r8, [rsp+38h+cbInit]; unsigned __int64 *
0x1800f97d7  call    ?ULongLongMult@@YAJ_K0PEA_K@Z; ULongLongMult(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x1800f97dc  mov     ebx, eax
0x1800f97de  test    eax, eax
0x1800f97e0  jns     short loc_1800F97FD
0x1800f97e2  mov     edx, 32h ; '2'; void *
0x1800f97e7  mov     rcx, [rsp+38h]; this
0x1800f97ec  mov     r9d, eax; char *
0x1800f97ef  lea     r8, aOnecoreuapAdmi_24; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x1800f97f6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800f97fb  jmp     short loc_1800F984B
0x1800f97fd  call    cs:__imp_RtlIsStateSeparationEnabled
0x1800f9804  nop     dword ptr [rax+rax+00h]
0x1800f9809  test    al, al
0x1800f980b  cmovz   rdi, r14
0x1800f980f  mov     edx, dword ptr [rsp+38h+cbInit]; cbInit
0x1800f9813  mov     rcx, rdi; pInit
0x1800f9816  call    cs:__imp_SHCreateMemStream
0x1800f981d  nop     dword ptr [rax+rax+00h]
0x1800f9822  mov     rdx, rax
0x1800f9825  lea     rcx, [rsp+38h+arg_10]
0x1800f982a  call    ??4?$ComPtr@UIStream@@@WRL@Microsoft@@QEAAAEAV012@PEAUIStream@@@Z; Microsoft::WRL::ComPtr<IStream>::operator=(IStream *)
0x1800f982f  mov     rdx, [rsi]; struct IStream *
0x1800f9832  mov     rcx, [rsp+38h+arg_10]; struct IStream *
0x1800f9837  call    ?CreateDiagnosticData@@YAJPEAUIStream@@0@Z; CreateDiagnosticData(IStream *,IStream *)
0x1800f983c  mov     ebx, eax
0x1800f983e  test    eax, eax
0x1800f9840  jns     short loc_1800F9849
0x1800f9842  mov     edx, 37h ; '7'
0x1800f9847  jmp     short loc_1800F97E7
0x1800f9849  mov     ebx, ebp
0x1800f984b  lea     rcx, [rsp+38h+arg_10]
0x1800f9850  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x1800f9855  mov     eax, ebx
0x1800f9857  mov     rbx, [rsp+38h+arg_0]
0x1800f985c  mov     rbp, [rsp+38h+arg_8]
0x1800f9861  add     rsp, 20h
0x1800f9865  pop     r14
0x1800f9867  pop     rdi
0x1800f9868  pop     rsi
0x1800f9869  retn
```
