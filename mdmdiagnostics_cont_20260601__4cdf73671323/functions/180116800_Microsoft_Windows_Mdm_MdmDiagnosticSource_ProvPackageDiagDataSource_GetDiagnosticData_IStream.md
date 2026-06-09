# Microsoft::Windows::Mdm::MdmDiagnosticSource::ProvPackageDiagDataSource::GetDiagnosticData(IStream * *)

- ea: `0x180116800`
- end: `0x1801168f2`
- name: `?GetDiagnosticData@ProvPackageDiagDataSource@MdmDiagnosticSource@Mdm@Windows@Microsoft@@UEAAJPEAPEAUIStream@@@Z`
- size: `242`
- prototype: `int(Microsoft::Windows::Mdm::MdmDiagnosticSource::ProvPackageDiagDataSource *__hidden this, struct IStream **)`
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x1800ead14`
- `0x1800ece5c`
- `0x1800f7f10`
- `0x1800f8680`
- `0x180116800`
- `0x180122018`

## import_xrefs

- `ntdll!RtlIsStateSeparationEnabled` at `0x180116839`
- `ntdll!RtlIsStateSeparationEnabled` at `0x180116891`
- `ntdll!RtlIsStateSeparationEnabled` at `0x180116839`
- `ntdll!RtlIsStateSeparationEnabled` at `0x180116891`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x180116828`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x180116828`
- `api-ms-win-shcore-stream-l1-1-0!SHCreateMemStream` at `0x1801168a4`
- `api-ms-win-shcore-stream-l1-1-0!SHCreateMemStream` at `0x1801168a4`

## string_xrefs

- `0x18011683f`: `<?xml version="1.0" encoding="utf-16"?>\n<DiagData>\n    <DataSource name="ProvisioningResults">\n        <Key>\n            <Category>Result</Category>\n            <Path>HKLM\Software\Microsoft\Provisioning\Results\*</Path>\n            <Representation>PackageId</Representation>\n            <Value>\n                <Name>PackageFileName</Name>\n                <ValueRepresentation>PackageFileName</ValueRepresentation>\n            </Value>\n            <Key>\n                <Category>Statist`
- `0x180116846`: `<?xml version="1.0" encoding="utf-16"?>\n<DiagData>\n    <DataSource name="OSDataProvisioningResults">\n        <Key>\n            <Category>Result</Category>\n            <Path>HKLM\OSData\Software\Microsoft\Provisioning\Results\*</Path>\n            <Representation>PackageId</Representation>\n            <Value>\n                <Name>PackageFileName</Name>\n                <ValueRepresentation>PackageFileName</ValueRepresentation>\n            </Value>\n            <Key>\n                <Cat`
- `0x180116883`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\dll\provpackagediagdata.cpp`

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
0x180116800  mov     rax, rsp
0x180116803  mov     [rax+8], rbx
0x180116807  mov     [rax+10h], rbp
0x18011680b  push    rsi
0x18011680c  push    rdi
0x18011680d  push    r14; int
0x18011680f  sub     rsp, 20h
0x180116813  mov     rsi, rdx
0x180116816  xor     ebp, ebp
0x180116818  mov     [rax+18h], rbp
0x18011681c  mov     [rax+20h], rbp
0x180116820  mov     r8, rdx; ppstm
0x180116823  lea     edx, [rbp+1]; fDeleteOnRelease
0x180116826  xor     ecx, ecx; hGlobal
0x180116828  call    cs:__imp_CreateStreamOnHGlobal
0x18011682e  mov     ebx, eax
0x180116830  test    eax, eax
0x180116832  jns     short loc_180116839
0x180116834  lea     edx, [rbp+31h]
0x180116837  jmp     short loc_18011687B
0x180116839  call    cs:__imp_RtlIsStateSeparationEnabled
0x18011683f  lea     r14, aXmlVersion10En_0; "<?xml version=\"1.0\" encoding=\"utf-16"...
0x180116846  lea     rdi, aXmlVersion10En_12; "<?xml version=\"1.0\" encoding=\"utf-16"...
0x18011684d  mov     rdx, rdi
0x180116850  test    al, al
0x180116852  cmovz   rdx, r14; unsigned __int64
0x180116856  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18011685a  inc     rcx
0x18011685d  cmp     [rdx+rcx*2], bp
0x180116861  jnz     short loc_18011685A
0x180116863  inc     rcx; unsigned __int64
0x180116866  lea     r8, [rsp+38h+cbInit]; unsigned __int64 *
0x18011686b  call    ?ULongLongMult@@YAJ_K0PEA_K@Z; ULongLongMult(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x180116870  mov     ebx, eax
0x180116872  test    eax, eax
0x180116874  jns     short loc_180116891
0x180116876  mov     edx, 32h ; '2'; void *
0x18011687b  mov     rcx, [rsp+38h]; this
0x180116880  mov     r9d, eax; char *
0x180116883  lea     r8, aOnecoreuapAdmi_36; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x18011688a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18011688f  jmp     short loc_1801168D3
0x180116891  call    cs:__imp_RtlIsStateSeparationEnabled
0x180116897  test    al, al
0x180116899  cmovz   rdi, r14
0x18011689d  mov     edx, dword ptr [rsp+38h+cbInit]; cbInit
0x1801168a1  mov     rcx, rdi; pInit
0x1801168a4  call    cs:__imp_SHCreateMemStream
0x1801168aa  mov     rdx, rax
0x1801168ad  lea     rcx, [rsp+38h+arg_10]
0x1801168b2  call    ??4?$ComPtr@UIStream@@@WRL@Microsoft@@QEAAAEAV012@PEAUIStream@@@Z; Microsoft::WRL::ComPtr<IStream>::operator=(IStream *)
0x1801168b7  mov     rdx, [rsi]; struct IStream *
0x1801168ba  mov     rcx, [rsp+38h+arg_10]; struct IStream *
0x1801168bf  call    ?CreateDiagnosticData@@YAJPEAUIStream@@0@Z; CreateDiagnosticData(IStream *,IStream *)
0x1801168c4  mov     ebx, eax
0x1801168c6  test    eax, eax
0x1801168c8  jns     short loc_1801168D1
0x1801168ca  mov     edx, 37h ; '7'
0x1801168cf  jmp     short loc_18011687B
0x1801168d1  mov     ebx, ebp
0x1801168d3  lea     rcx, [rsp+38h+arg_10]
0x1801168d8  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x1801168dd  mov     eax, ebx
0x1801168df  mov     rbx, [rsp+38h+arg_0]
0x1801168e4  mov     rbp, [rsp+38h+arg_8]
0x1801168e9  add     rsp, 20h
0x1801168ed  pop     r14
0x1801168ef  pop     rdi
0x1801168f0  pop     rsi
0x1801168f1  retn
```
