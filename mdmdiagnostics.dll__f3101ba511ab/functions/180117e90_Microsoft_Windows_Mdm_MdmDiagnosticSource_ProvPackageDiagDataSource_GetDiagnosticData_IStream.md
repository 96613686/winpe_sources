# Microsoft::Windows::Mdm::MdmDiagnosticSource::ProvPackageDiagDataSource::GetDiagnosticData(IStream * *)

- ea: `0x180117e90`
- end: `0x180117f9b`
- name: `?GetDiagnosticData@ProvPackageDiagDataSource@MdmDiagnosticSource@Mdm@Windows@Microsoft@@UEAAJPEAPEAUIStream@@@Z`
- size: `267`
- prototype: `int(Microsoft::Windows::Mdm::MdmDiagnosticSource::ProvPackageDiagDataSource *__hidden this, struct IStream **)`
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x1800eb1ac`
- `0x1800ed46c`
- `0x1800f8e70`
- `0x1800f962c`
- `0x180117e90`
- `0x180123aa8`

## import_xrefs

- `ntdll!RtlIsStateSeparationEnabled` at `0x180117ecf`
- `ntdll!RtlIsStateSeparationEnabled` at `0x180117f2d`
- `ntdll!RtlIsStateSeparationEnabled` at `0x180117ecf`
- `ntdll!RtlIsStateSeparationEnabled` at `0x180117f2d`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x180117eb8`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x180117eb8`
- `api-ms-win-shcore-stream-l1-1-0!SHCreateMemStream` at `0x180117f46`
- `api-ms-win-shcore-stream-l1-1-0!SHCreateMemStream` at `0x180117f46`

## string_xrefs

- `0x180117ee2`: `<?xml version="1.0" encoding="utf-16"?>\n<DiagData>\n    <DataSource name="OSDataProvisioningResults">\n        <Key>\n            <Category>Result</Category>\n            <Path>HKLM\OSData\Software\Microsoft\Provisioning\Results\*</Path>\n            <Representation>PackageId</Representation>\n            <Value>\n                <Name>PackageFileName</Name>\n                <ValueRepresentation>PackageFileName</ValueRepresentation>\n            </Value>\n            <Key>\n                <Cat`
- `0x180117edb`: `<?xml version="1.0" encoding="utf-16"?>\n<DiagData>\n    <DataSource name="ProvisioningResults">\n        <Key>\n            <Category>Result</Category>\n            <Path>HKLM\Software\Microsoft\Provisioning\Results\*</Path>\n            <Representation>PackageId</Representation>\n            <Value>\n                <Name>PackageFileName</Name>\n                <ValueRepresentation>PackageFileName</ValueRepresentation>\n            </Value>\n            <Key>\n                <Category>Statist`
- `0x180117f1f`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\dll\provpackagediagdata.cpp`

## pseudocode

```c
__int64 __fastcall Microsoft::Windows::Mdm::MdmDiagnosticSource::ProvPackageDiagDataSource::GetDiagnosticData(
        Microsoft::Windows::Mdm::MdmDiagnosticSource::ProvPackageDiagDataSource *this,
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
                        "    <DataSource name=\"OSDataProvisioningResults\">\n"
                        "        <Key>\n"
                        "            <Category>Result</Category>\n"
                        "            <Path>HKLM\\OSData\\Software\\Microsoft\\Provisioning\\Results\\*</Path>\n"
                        "            <Representation>PackageId</Representation>\n"
                        "            <Value>\n"
                        "                <Name>PackageFileName</Name>\n"
                        "                <ValueRepresentation>PackageFileName</ValueRepresentation>\n"
                        "            </Value>\n"
                        "            <Key>\n"
                        "                <Category>Statistics</Category>\n"
                        "                <Representation>Area</Representation>\n"
                        "                <Path>*</Path>\n"
                        "                <Key>\n"
                        "                    <Category>General</Category>\n"
                        "                    <Representation>Info</Representation>\n"
                        "                    <Path>*</Path>\n"
                        "                    <Key>\n"
                        "                        <Category>XML</Category>\n"
                        "                        <Representation>XMLName</Representation>\n"
                        "                        <Path>*</Path>\n"
                        "                        <Value>\n"
                        "                            <Name>Categories</Name>\n"
                        "                            <ValueRepresentation>Categories</ValueRepresentation>\n"
                        "                        </Value>\n"
                        "                        <Value>\n"
                        "                            <Name>Message</Name>\n"
                        "                            <ValueRepresentation>Message</ValueRepresentation>\n"
                        "                        </Value>\n"
                        "                        <Value>\n"
                        "                            <Name>LastResult</Name>\n"
                        "                            <ValueRepresentation>LastResult</ValueRepresentation>\n"
                        "                        </Value>\n"
                        "                        <Value>\n"
                        "                            <Name>NumFailures</Name>\n"
                        "                            <ValueRepresentation>NumberOfFailures</ValueRepresentation>\n"
                        "                        </Value>\n"
                        "                        <Value>\n"
                        "                            <Name>FailingNodePath</Name>\n"
                        "                            <ValueRepresentation>FailingNodePath</ValueRepresentation>\n"
                        "                        </Value>\n"
                        "                    </Key>\n"
                        "                </Key>\n"
                        "            </Key>\n"
                        "        </Key>\n"
                        "    </DataSource>\n"
                        "</DiagData>";
    v8 = L"<?xml version=\"1.0\" encoding=\"utf-16\"?>\n"
          "<DiagData>\n"
          "    <DataSource name=\"OSDataProvisioningResults\">\n"
          "        <Key>\n"
          "            <Category>Result</Category>\n"
          "            <Path>HKLM\\OSData\\Software\\Microsoft\\Provisioning\\Results\\*</Path>\n"
          "            <Representation>PackageId</Representation>\n"
          "            <Value>\n"
          "                <Name>PackageFileName</Name>\n"
          "                <ValueRepresentation>PackageFileName</ValueRepresentation>\n"
          "            </Value>\n"
          "            <Key>\n"
          "                <Category>Statistics</Category>\n"
          "                <Representation>Area</Representation>\n"
          "                <Path>*</Path>\n"
          "                <Key>\n"
          "                    <Category>General</Category>\n"
          "                    <Representation>Info</Representation>\n"
          "                    <Path>*</Path>\n"
          "                    <Key>\n"
          "                        <Category>XML</Category>\n"
          "                        <Representation>XMLName</Representation>\n"
          "                        <Path>*</Path>\n"
          "                        <Value>\n"
          "                            <Name>Categories</Name>\n"
          "                            <ValueRepresentation>Categories</ValueRepresentation>\n"
          "                        </Value>\n"
          "                        <Value>\n"
          "                            <Name>Message</Name>\n"
          "                            <ValueRepresentation>Message</ValueRepresentation>\n"
          "                        </Value>\n"
          "                        <Value>\n"
          "                            <Name>LastResult</Name>\n"
          "                            <ValueRepresentation>LastResult</ValueRepresentation>\n"
          "                        </Value>\n"
          "                        <Value>\n"
          "                            <Name>NumFailures</Name>\n"
          "                            <ValueRepresentation>NumberOfFailures</ValueRepresentation>\n"
          "                        </Value>\n"
          "                        <Value>\n"
          "                            <Name>FailingNodePath</Name>\n"
          "                            <ValueRepresentation>FailingNodePath</ValueRepresentation>\n"
          "                        </Value>\n"
          "                    </Key>\n"
          "                </Key>\n"
          "            </Key>\n"
          "        </Key>\n"
          "    </DataSource>\n"
          "</DiagData>";
    if ( !IsStateSeparationEnabled )
      v8 = (const wchar_t *)L"<?xml version=\"1.0\" encoding=\"utf-16\"?>\n"
                             "<DiagData>\n"
                             "    <DataSource name=\"ProvisioningResults\">\n"
                             "        <Key>\n"
                             "            <Category>Result</Category>\n"
                             "            <Path>HKLM\\Software\\Microsoft\\Provisioning\\Results\\*</Path>\n"
                             "            <Representation>PackageId</Representation>\n"
                             "            <Value>\n"
                             "                <Name>PackageFileName</Name>\n"
                             "                <ValueRepresentation>PackageFileName</ValueRepresentation>\n"
                             "            </Value>\n"
                             "            <Key>\n"
                             "                <Category>Statistics</Category>\n"
                             "                <Representation>Area</Representation>\n"
                             "                <Path>*</Path>\n"
                             "                <Key>\n"
                             "                    <Category>General</Category>\n"
                             "                    <Representation>Info</Representation>\n"
                             "                    <Path>*</Path>\n"
                             "                    <Key>\n"
                             "                        <Category>XML</Category>\n"
                             "                        <Representation>XMLName</Representation>\n"
                             "                        <Path>*</Path>\n"
                             "                        <Value>\n"
                             "                            <Name>Categories</Name>\n"
                             "                            <ValueRepresentation>Categories</ValueRepresentation>\n"
                             "                        </Value>\n"
                             "                        <Value>\n"
                             "                            <Name>Message</Name>\n"
                             "                            <ValueRepresentation>Message</ValueRepresentation>\n"
                             "                        </Value>\n"
                             "                        <Value>\n"
                             "                            <Name>LastResult</Name>\n"
                             "                            <ValueRepresentation>LastResult</ValueRepresentation>\n"
                             "                        </Value>\n"
                             "                        <Value>\n"
                             "                            <Name>NumFailures</Name>\n"
                             "                            <ValueRepresentation>NumberOfFailures</ValueRepresentation>\n"
                             "                        </Value>\n"
                             "                        <Value>\n"
                             "                            <Name>FailingNodePath</Name>\n"
                             "                            <ValueRepresentation>FailingNodePath</ValueRepresentation>\n"
                             "                        </Value>\n"
                             "                    </Key>\n"
                             "                </Key>\n"
                             "            </Key>\n"
                             "        </Key>\n"
                             "    </DataSource>\n"
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
              "    <DataSource name=\"ProvisioningResults\">\n"
              "        <Key>\n"
              "            <Category>Result</Category>\n"
              "            <Path>HKLM\\Software\\Microsoft\\Provisioning\\Results\\*</Path>\n"
              "            <Representation>PackageId</Representation>\n"
              "            <Value>\n"
              "                <Name>PackageFileName</Name>\n"
              "                <ValueRepresentation>PackageFileName</ValueRepresentation>\n"
              "            </Value>\n"
              "            <Key>\n"
              "                <Category>Statistics</Category>\n"
              "                <Representation>Area</Representation>\n"
              "                <Path>*</Path>\n"
              "                <Key>\n"
              "                    <Category>General</Category>\n"
              "                    <Representation>Info</Representation>\n"
              "                    <Path>*</Path>\n"
              "                    <Key>\n"
              "                        <Category>XML</Category>\n"
              "                        <Representation>XMLName</Representation>\n"
              "                        <Path>*</Path>\n"
              "                        <Value>\n"
              "                            <Name>Categories</Name>\n"
              "                            <ValueRepresentation>Categories</ValueRepresentation>\n"
              "                        </Value>\n"
              "                        <Value>\n"
              "                            <Name>Message</Name>\n"
              "                            <ValueRepresentation>Message</ValueRepresentation>\n"
              "                        </Value>\n"
              "                        <Value>\n"
              "                            <Name>LastResult</Name>\n"
              "                            <ValueRepresentation>LastResult</ValueRepresentation>\n"
              "                        </Value>\n"
              "                        <Value>\n"
              "                            <Name>NumFailures</Name>\n"
              "                            <ValueRepresentation>NumberOfFailures</ValueRepresentation>\n"
              "                        </Value>\n"
              "                        <Value>\n"
              "                            <Name>FailingNodePath</Name>\n"
              "                            <ValueRepresentation>FailingNodePath</ValueRepresentation>\n"
              "                        </Value>\n"
              "                    </Key>\n"
              "                </Key>\n"
              "            </Key>\n"
              "        </Key>\n"
              "    </DataSource>\n"
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
    (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmdiagnostics\\dll\\provpackagediagdata.cpp",
    (const char *)(unsigned int)StreamOnHGlobal,
    v12);
LABEL_15:
  Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&v14);
  return v4;
}

```

## disassembly

```asm
0x180117e90  mov     rax, rsp
0x180117e93  mov     [rax+8], rbx
0x180117e97  mov     [rax+10h], rbp
0x180117e9b  push    rsi
0x180117e9c  push    rdi
0x180117e9d  push    r14; int
0x180117e9f  sub     rsp, 20h
0x180117ea3  mov     rsi, rdx
0x180117ea6  xor     ebp, ebp
0x180117ea8  mov     [rax+18h], rbp
0x180117eac  mov     [rax+20h], rbp
0x180117eb0  mov     r8, rdx; ppstm
0x180117eb3  lea     edx, [rbp+1]; fDeleteOnRelease
0x180117eb6  xor     ecx, ecx; hGlobal
0x180117eb8  call    cs:__imp_CreateStreamOnHGlobal
0x180117ebf  nop     dword ptr [rax+rax+00h]
0x180117ec4  mov     ebx, eax
0x180117ec6  test    eax, eax
0x180117ec8  jns     short loc_180117ECF
0x180117eca  lea     edx, [rbp+31h]
0x180117ecd  jmp     short loc_180117F17
0x180117ecf  call    cs:__imp_RtlIsStateSeparationEnabled
0x180117ed6  nop     dword ptr [rax+rax+00h]
0x180117edb  lea     r14, aXmlVersion10En_0; "<?xml version=\"1.0\" encoding=\"utf-16"...
0x180117ee2  lea     rdi, aXmlVersion10En_12; "<?xml version=\"1.0\" encoding=\"utf-16"...
0x180117ee9  mov     rdx, rdi
0x180117eec  test    al, al
0x180117eee  cmovz   rdx, r14; unsigned __int64
0x180117ef2  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180117ef6  inc     rcx
0x180117ef9  cmp     [rdx+rcx*2], bp
0x180117efd  jnz     short loc_180117EF6
0x180117eff  inc     rcx; unsigned __int64
0x180117f02  lea     r8, [rsp+38h+cbInit]; unsigned __int64 *
0x180117f07  call    ?ULongLongMult@@YAJ_K0PEA_K@Z; ULongLongMult(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x180117f0c  mov     ebx, eax
0x180117f0e  test    eax, eax
0x180117f10  jns     short loc_180117F2D
0x180117f12  mov     edx, 32h ; '2'; void *
0x180117f17  mov     rcx, [rsp+38h]; this
0x180117f1c  mov     r9d, eax; char *
0x180117f1f  lea     r8, aOnecoreuapAdmi_36; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x180117f26  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180117f2b  jmp     short loc_180117F7B
0x180117f2d  call    cs:__imp_RtlIsStateSeparationEnabled
0x180117f34  nop     dword ptr [rax+rax+00h]
0x180117f39  test    al, al
0x180117f3b  cmovz   rdi, r14
0x180117f3f  mov     edx, dword ptr [rsp+38h+cbInit]; cbInit
0x180117f43  mov     rcx, rdi; pInit
0x180117f46  call    cs:__imp_SHCreateMemStream
0x180117f4d  nop     dword ptr [rax+rax+00h]
0x180117f52  mov     rdx, rax
0x180117f55  lea     rcx, [rsp+38h+arg_10]
0x180117f5a  call    ??4?$ComPtr@UIStream@@@WRL@Microsoft@@QEAAAEAV012@PEAUIStream@@@Z; Microsoft::WRL::ComPtr<IStream>::operator=(IStream *)
0x180117f5f  mov     rdx, [rsi]; struct IStream *
0x180117f62  mov     rcx, [rsp+38h+arg_10]; struct IStream *
0x180117f67  call    ?CreateDiagnosticData@@YAJPEAUIStream@@0@Z; CreateDiagnosticData(IStream *,IStream *)
0x180117f6c  mov     ebx, eax
0x180117f6e  test    eax, eax
0x180117f70  jns     short loc_180117F79
0x180117f72  mov     edx, 37h ; '7'
0x180117f77  jmp     short loc_180117F17
0x180117f79  mov     ebx, ebp
0x180117f7b  lea     rcx, [rsp+38h+arg_10]
0x180117f80  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x180117f85  mov     eax, ebx
0x180117f87  mov     rbx, [rsp+38h+arg_0]
0x180117f8c  mov     rbp, [rsp+38h+arg_8]
0x180117f91  add     rsp, 20h
0x180117f95  pop     r14
0x180117f97  pop     rdi
0x180117f98  pop     rsi
0x180117f99  retn
```
