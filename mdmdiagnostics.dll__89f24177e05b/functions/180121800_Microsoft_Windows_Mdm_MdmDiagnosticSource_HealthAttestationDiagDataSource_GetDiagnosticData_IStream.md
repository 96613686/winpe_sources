# Microsoft::Windows::Mdm::MdmDiagnosticSource::HealthAttestationDiagDataSource::GetDiagnosticData(IStream * *)

- ea: `0x180121800`
- end: `0x1801218f2`
- name: `?GetDiagnosticData@HealthAttestationDiagDataSource@MdmDiagnosticSource@Mdm@Windows@Microsoft@@UEAAJPEAPEAUIStream@@@Z`
- size: `242`
- prototype: `int(Microsoft::Windows::Mdm::MdmDiagnosticSource::HealthAttestationDiagDataSource *__hidden this, struct IStream **)`
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x1800ead14`
- `0x1800ece5c`
- `0x1800f7f10`
- `0x1800f8680`
- `0x180121800`
- `0x180122018`

## import_xrefs

- `ntdll!RtlIsStateSeparationEnabled` at `0x180121839`
- `ntdll!RtlIsStateSeparationEnabled` at `0x180121891`
- `ntdll!RtlIsStateSeparationEnabled` at `0x180121839`
- `ntdll!RtlIsStateSeparationEnabled` at `0x180121891`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x180121828`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x180121828`
- `api-ms-win-shcore-stream-l1-1-0!SHCreateMemStream` at `0x1801218a4`
- `api-ms-win-shcore-stream-l1-1-0!SHCreateMemStream` at `0x1801218a4`

## string_xrefs

- `0x180121846`: `<?xml version="1.0" encoding="utf-16"?>\n<DiagData>\n  <DataSource name="HealthAttestation">\n    <Key>\n      <Category>HealthAttestation</Category>\n      <Path>HKLM\OSDATA\SOFTWARE\Microsoft\Windows\HealthAttestationAttestClient</Path>\n      <Representation>Health Attestation</Representation>\n      <Value>\n          <Name>*</Name>\n          <ValueRepresentation>DiagnosticValue</ValueRepresentation>\n      </Value>\n    </Key>\n    <Key>\n      <Category>DHA</Category>\n      <Path>HKLM\OS`
- `0x18012183f`: `<?xml version="1.0" encoding="utf-16"?>\n<DiagData>\n  <DataSource name="HealthAttestation">\n    <Key>\n      <Category>HealthAttestation</Category>\n      <Path>HKLM\SOFTWARE\Microsoft\Windows\HealthAttestationAttestClient</Path>\n      <Representation>Type</Representation>\n      <Value>\n          <Name>*</Name>\n          <ValueRepresentation>DiagnosticValue</ValueRepresentation>\n      </Value>\n    </Key>\n    <Key>\n      <Category>DHA</Category>\n      <Path>HKLM\SYSTEM\CurrentControlSe`
- `0x180121883`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\dll\healthattestationdiagdata.cpp`

## pseudocode

```c
__int64 __fastcall Microsoft::Windows::Mdm::MdmDiagnosticSource::HealthAttestationDiagDataSource::GetDiagnosticData(
        Microsoft::Windows::Mdm::MdmDiagnosticSource::HealthAttestationDiagDataSource *this,
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
                        "  <DataSource name=\"HealthAttestation\">\n"
                        "    <Key>\n"
                        "      <Category>HealthAttestation</Category>\n"
                        "      <Path>HKLM\\OSDATA\\SOFTWARE\\Microsoft\\Windows\\HealthAttestationAttestClient</Path>\n"
                        "      <Representation>Health Attestation</Representation>\n"
                        "      <Value>\n"
                        "          <Name>*</Name>\n"
                        "          <ValueRepresentation>DiagnosticValue</ValueRepresentation>\n"
                        "      </Value>\n"
                        "    </Key>\n"
                        "    <Key>\n"
                        "      <Category>DHA</Category>\n"
                        "      <Path>HKLM\\OSDATA\\SYSTEM\\CurrentControlSet\\Services\\TPM\\WMI\\HealthCert\\Store</Path"
                        ">\n"
                        "      <Representation>DHAParentKey</Representation>\n"
                        "      <Value>\n"
                        "          <Name>*</Name>\n"
                        "          <ValueRepresentation>*</ValueRepresentation>\n"
                        "      </Value>\n"
                        "      <Key>\n"
                        "        <Category>Server</Category>\n"
                        "        <Path>*</Path>\n"
                        "        <Representation>Server</Representation>\n"
                        "        <Value>\n"
                        "            <Name>*</Name>\n"
                        "            <ValueRepresentation>*</ValueRepresentation>\n"
                        "        </Value>\n"
                        "        <Key>\n"
                        "            <Category>HealthCertificate</Category>\n"
                        "            <Path>HealthCertificate</Path>\n"
                        "            <Representation>HealthCertificate</Representation>\n"
                        "            <Value>\n"
                        "                <Name>*</Name>\n"
                        "                <ValueRepresentation>*</ValueRepresentation>\n"
                        "            </Value>\n"
                        "        </Key>\n"
                        "      </Key>\n"
                        "    </Key>\n"
                        "  </DataSource>\n"
                        "</DiagData>";
    v8 = L"<?xml version=\"1.0\" encoding=\"utf-16\"?>\n"
          "<DiagData>\n"
          "  <DataSource name=\"HealthAttestation\">\n"
          "    <Key>\n"
          "      <Category>HealthAttestation</Category>\n"
          "      <Path>HKLM\\OSDATA\\SOFTWARE\\Microsoft\\Windows\\HealthAttestationAttestClient</Path>\n"
          "      <Representation>Health Attestation</Representation>\n"
          "      <Value>\n"
          "          <Name>*</Name>\n"
          "          <ValueRepresentation>DiagnosticValue</ValueRepresentation>\n"
          "      </Value>\n"
          "    </Key>\n"
          "    <Key>\n"
          "      <Category>DHA</Category>\n"
          "      <Path>HKLM\\OSDATA\\SYSTEM\\CurrentControlSet\\Services\\TPM\\WMI\\HealthCert\\Store</Path>\n"
          "      <Representation>DHAParentKey</Representation>\n"
          "      <Value>\n"
          "          <Name>*</Name>\n"
          "          <ValueRepresentation>*</ValueRepresentation>\n"
          "      </Value>\n"
          "      <Key>\n"
          "        <Category>Server</Category>\n"
          "        <Path>*</Path>\n"
          "        <Representation>Server</Representation>\n"
          "        <Value>\n"
          "            <Name>*</Name>\n"
          "            <ValueRepresentation>*</ValueRepresentation>\n"
          "        </Value>\n"
          "        <Key>\n"
          "            <Category>HealthCertificate</Category>\n"
          "            <Path>HealthCertificate</Path>\n"
          "            <Representation>HealthCertificate</Representation>\n"
          "            <Value>\n"
          "                <Name>*</Name>\n"
          "                <ValueRepresentation>*</ValueRepresentation>\n"
          "            </Value>\n"
          "        </Key>\n"
          "      </Key>\n"
          "    </Key>\n"
          "  </DataSource>\n"
          "</DiagData>";
    if ( !IsStateSeparationEnabled )
      v8 = (const wchar_t *)L"<?xml version=\"1.0\" encoding=\"utf-16\"?>\n"
                             "<DiagData>\n"
                             "  <DataSource name=\"HealthAttestation\">\n"
                             "    <Key>\n"
                             "      <Category>HealthAttestation</Category>\n"
                             "      <Path>HKLM\\SOFTWARE\\Microsoft\\Windows\\HealthAttestationAttestClient</Path>\n"
                             "      <Representation>Type</Representation>\n"
                             "      <Value>\n"
                             "          <Name>*</Name>\n"
                             "          <ValueRepresentation>DiagnosticValue</ValueRepresentation>\n"
                             "      </Value>\n"
                             "    </Key>\n"
                             "    <Key>\n"
                             "      <Category>DHA</Category>\n"
                             "      <Path>HKLM\\SYSTEM\\CurrentControlSet\\Services\\TPM\\WMI\\HealthCert\\Store</Path>\n"
                             "      <Representation>Type</Representation>\n"
                             "      <Value>\n"
                             "          <Name>*</Name>\n"
                             "          <ValueRepresentation>*</ValueRepresentation>\n"
                             "      </Value>\n"
                             "      <Key>\n"
                             "        <Category>Server</Category>\n"
                             "        <Path>*</Path>\n"
                             "        <Representation>Server</Representation>\n"
                             "        <Value>\n"
                             "            <Name>*</Name>\n"
                             "            <ValueRepresentation>*</ValueRepresentation>\n"
                             "        </Value>\n"
                             "        <Key>\n"
                             "            <Category>HealthCertificate</Category>\n"
                             "            <Path>HealthCertificate</Path>\n"
                             "            <Representation>HealthCertificate</Representation>\n"
                             "            <Value>\n"
                             "                <Name>*</Name>\n"
                             "                <ValueRepresentation>*</ValueRepresentation>\n"
                             "            </Value>\n"
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
              "  <DataSource name=\"HealthAttestation\">\n"
              "    <Key>\n"
              "      <Category>HealthAttestation</Category>\n"
              "      <Path>HKLM\\SOFTWARE\\Microsoft\\Windows\\HealthAttestationAttestClient</Path>\n"
              "      <Representation>Type</Representation>\n"
              "      <Value>\n"
              "          <Name>*</Name>\n"
              "          <ValueRepresentation>DiagnosticValue</ValueRepresentation>\n"
              "      </Value>\n"
              "    </Key>\n"
              "    <Key>\n"
              "      <Category>DHA</Category>\n"
              "      <Path>HKLM\\SYSTEM\\CurrentControlSet\\Services\\TPM\\WMI\\HealthCert\\Store</Path>\n"
              "      <Representation>Type</Representation>\n"
              "      <Value>\n"
              "          <Name>*</Name>\n"
              "          <ValueRepresentation>*</ValueRepresentation>\n"
              "      </Value>\n"
              "      <Key>\n"
              "        <Category>Server</Category>\n"
              "        <Path>*</Path>\n"
              "        <Representation>Server</Representation>\n"
              "        <Value>\n"
              "            <Name>*</Name>\n"
              "            <ValueRepresentation>*</ValueRepresentation>\n"
              "        </Value>\n"
              "        <Key>\n"
              "            <Category>HealthCertificate</Category>\n"
              "            <Path>HealthCertificate</Path>\n"
              "            <Representation>HealthCertificate</Representation>\n"
              "            <Value>\n"
              "                <Name>*</Name>\n"
              "                <ValueRepresentation>*</ValueRepresentation>\n"
              "            </Value>\n"
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
    (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmdiagnostics\\dll\\healthattestationdiagdata.cpp",
    (const char *)(unsigned int)StreamOnHGlobal,
    v12);
LABEL_15:
  Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&v14);
  return v4;
}

```

## disassembly

```asm
0x180121800  mov     rax, rsp
0x180121803  mov     [rax+8], rbx
0x180121807  mov     [rax+10h], rbp
0x18012180b  push    rsi
0x18012180c  push    rdi
0x18012180d  push    r14; int
0x18012180f  sub     rsp, 20h
0x180121813  mov     rsi, rdx
0x180121816  xor     ebp, ebp
0x180121818  mov     [rax+18h], rbp
0x18012181c  mov     [rax+20h], rbp
0x180121820  mov     r8, rdx; ppstm
0x180121823  lea     edx, [rbp+1]; fDeleteOnRelease
0x180121826  xor     ecx, ecx; hGlobal
0x180121828  call    cs:__imp_CreateStreamOnHGlobal
0x18012182e  mov     ebx, eax
0x180121830  test    eax, eax
0x180121832  jns     short loc_180121839
0x180121834  lea     edx, [rbp+31h]
0x180121837  jmp     short loc_18012187B
0x180121839  call    cs:__imp_RtlIsStateSeparationEnabled
0x18012183f  lea     r14, aXmlVersion10En_28; "<?xml version=\"1.0\" encoding=\"utf-16"...
0x180121846  lea     rdi, aXmlVersion10En_2; "<?xml version=\"1.0\" encoding=\"utf-16"...
0x18012184d  mov     rdx, rdi
0x180121850  test    al, al
0x180121852  cmovz   rdx, r14; unsigned __int64
0x180121856  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18012185a  inc     rcx
0x18012185d  cmp     [rdx+rcx*2], bp
0x180121861  jnz     short loc_18012185A
0x180121863  inc     rcx; unsigned __int64
0x180121866  lea     r8, [rsp+38h+cbInit]; unsigned __int64 *
0x18012186b  call    ?ULongLongMult@@YAJ_K0PEA_K@Z; ULongLongMult(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x180121870  mov     ebx, eax
0x180121872  test    eax, eax
0x180121874  jns     short loc_180121891
0x180121876  mov     edx, 32h ; '2'; void *
0x18012187b  mov     rcx, [rsp+38h]; this
0x180121880  mov     r9d, eax; char *
0x180121883  lea     r8, aOnecoreuapAdmi_16; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x18012188a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18012188f  jmp     short loc_1801218D3
0x180121891  call    cs:__imp_RtlIsStateSeparationEnabled
0x180121897  test    al, al
0x180121899  cmovz   rdi, r14
0x18012189d  mov     edx, dword ptr [rsp+38h+cbInit]; cbInit
0x1801218a1  mov     rcx, rdi; pInit
0x1801218a4  call    cs:__imp_SHCreateMemStream
0x1801218aa  mov     rdx, rax
0x1801218ad  lea     rcx, [rsp+38h+arg_10]
0x1801218b2  call    ??4?$ComPtr@UIStream@@@WRL@Microsoft@@QEAAAEAV012@PEAUIStream@@@Z; Microsoft::WRL::ComPtr<IStream>::operator=(IStream *)
0x1801218b7  mov     rdx, [rsi]; struct IStream *
0x1801218ba  mov     rcx, [rsp+38h+arg_10]; struct IStream *
0x1801218bf  call    ?CreateDiagnosticData@@YAJPEAUIStream@@0@Z; CreateDiagnosticData(IStream *,IStream *)
0x1801218c4  mov     ebx, eax
0x1801218c6  test    eax, eax
0x1801218c8  jns     short loc_1801218D1
0x1801218ca  mov     edx, 37h ; '7'
0x1801218cf  jmp     short loc_18012187B
0x1801218d1  mov     ebx, ebp
0x1801218d3  lea     rcx, [rsp+38h+arg_10]
0x1801218d8  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x1801218dd  mov     eax, ebx
0x1801218df  mov     rbx, [rsp+38h+arg_0]
0x1801218e4  mov     rbp, [rsp+38h+arg_8]
0x1801218e9  add     rsp, 20h
0x1801218ed  pop     r14
0x1801218ef  pop     rdi
0x1801218f0  pop     rsi
0x1801218f1  retn
```
