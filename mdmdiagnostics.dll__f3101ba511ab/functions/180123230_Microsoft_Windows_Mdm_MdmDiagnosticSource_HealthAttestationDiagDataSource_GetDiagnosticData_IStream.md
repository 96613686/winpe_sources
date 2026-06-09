# Microsoft::Windows::Mdm::MdmDiagnosticSource::HealthAttestationDiagDataSource::GetDiagnosticData(IStream * *)

- ea: `0x180123230`
- end: `0x18012333b`
- name: `?GetDiagnosticData@HealthAttestationDiagDataSource@MdmDiagnosticSource@Mdm@Windows@Microsoft@@UEAAJPEAPEAUIStream@@@Z`
- size: `267`
- prototype: `int(Microsoft::Windows::Mdm::MdmDiagnosticSource::HealthAttestationDiagDataSource *__hidden this, struct IStream **)`
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x1800eb1ac`
- `0x1800ed46c`
- `0x1800f8e70`
- `0x1800f962c`
- `0x180123230`
- `0x180123aa8`

## import_xrefs

- `ntdll!RtlIsStateSeparationEnabled` at `0x18012326f`
- `ntdll!RtlIsStateSeparationEnabled` at `0x1801232cd`
- `ntdll!RtlIsStateSeparationEnabled` at `0x18012326f`
- `ntdll!RtlIsStateSeparationEnabled` at `0x1801232cd`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x180123258`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x180123258`
- `api-ms-win-shcore-stream-l1-1-0!SHCreateMemStream` at `0x1801232e6`
- `api-ms-win-shcore-stream-l1-1-0!SHCreateMemStream` at `0x1801232e6`

## string_xrefs

- `0x18012327b`: `<?xml version="1.0" encoding="utf-16"?>\n<DiagData>\n  <DataSource name="HealthAttestation">\n    <Key>\n      <Category>HealthAttestation</Category>\n      <Path>HKLM\SOFTWARE\Microsoft\Windows\HealthAttestationAttestClient</Path>\n      <Representation>Type</Representation>\n      <Value>\n          <Name>*</Name>\n          <ValueRepresentation>DiagnosticValue</ValueRepresentation>\n      </Value>\n    </Key>\n    <Key>\n      <Category>DHA</Category>\n      <Path>HKLM\SYSTEM\CurrentControlSe`
- `0x180123282`: `<?xml version="1.0" encoding="utf-16"?>\n<DiagData>\n  <DataSource name="HealthAttestation">\n    <Key>\n      <Category>HealthAttestation</Category>\n      <Path>HKLM\OSDATA\SOFTWARE\Microsoft\Windows\HealthAttestationAttestClient</Path>\n      <Representation>Health Attestation</Representation>\n      <Value>\n          <Name>*</Name>\n          <ValueRepresentation>DiagnosticValue</ValueRepresentation>\n      </Value>\n    </Key>\n    <Key>\n      <Category>DHA</Category>\n      <Path>HKLM\OS`
- `0x1801232bf`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\dll\healthattestationdiagdata.cpp`

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
0x180123230  mov     rax, rsp
0x180123233  mov     [rax+8], rbx
0x180123237  mov     [rax+10h], rbp
0x18012323b  push    rsi
0x18012323c  push    rdi
0x18012323d  push    r14; int
0x18012323f  sub     rsp, 20h
0x180123243  mov     rsi, rdx
0x180123246  xor     ebp, ebp
0x180123248  mov     [rax+18h], rbp
0x18012324c  mov     [rax+20h], rbp
0x180123250  mov     r8, rdx; ppstm
0x180123253  lea     edx, [rbp+1]; fDeleteOnRelease
0x180123256  xor     ecx, ecx; hGlobal
0x180123258  call    cs:__imp_CreateStreamOnHGlobal
0x18012325f  nop     dword ptr [rax+rax+00h]
0x180123264  mov     ebx, eax
0x180123266  test    eax, eax
0x180123268  jns     short loc_18012326F
0x18012326a  lea     edx, [rbp+31h]
0x18012326d  jmp     short loc_1801232B7
0x18012326f  call    cs:__imp_RtlIsStateSeparationEnabled
0x180123276  nop     dword ptr [rax+rax+00h]
0x18012327b  lea     r14, aXmlVersion10En_28; "<?xml version=\"1.0\" encoding=\"utf-16"...
0x180123282  lea     rdi, aXmlVersion10En_2; "<?xml version=\"1.0\" encoding=\"utf-16"...
0x180123289  mov     rdx, rdi
0x18012328c  test    al, al
0x18012328e  cmovz   rdx, r14; unsigned __int64
0x180123292  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180123296  inc     rcx
0x180123299  cmp     [rdx+rcx*2], bp
0x18012329d  jnz     short loc_180123296
0x18012329f  inc     rcx; unsigned __int64
0x1801232a2  lea     r8, [rsp+38h+cbInit]; unsigned __int64 *
0x1801232a7  call    ?ULongLongMult@@YAJ_K0PEA_K@Z; ULongLongMult(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x1801232ac  mov     ebx, eax
0x1801232ae  test    eax, eax
0x1801232b0  jns     short loc_1801232CD
0x1801232b2  mov     edx, 32h ; '2'; void *
0x1801232b7  mov     rcx, [rsp+38h]; this
0x1801232bc  mov     r9d, eax; char *
0x1801232bf  lea     r8, aOnecoreuapAdmi_16; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x1801232c6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801232cb  jmp     short loc_18012331B
0x1801232cd  call    cs:__imp_RtlIsStateSeparationEnabled
0x1801232d4  nop     dword ptr [rax+rax+00h]
0x1801232d9  test    al, al
0x1801232db  cmovz   rdi, r14
0x1801232df  mov     edx, dword ptr [rsp+38h+cbInit]; cbInit
0x1801232e3  mov     rcx, rdi; pInit
0x1801232e6  call    cs:__imp_SHCreateMemStream
0x1801232ed  nop     dword ptr [rax+rax+00h]
0x1801232f2  mov     rdx, rax
0x1801232f5  lea     rcx, [rsp+38h+arg_10]
0x1801232fa  call    ??4?$ComPtr@UIStream@@@WRL@Microsoft@@QEAAAEAV012@PEAUIStream@@@Z; Microsoft::WRL::ComPtr<IStream>::operator=(IStream *)
0x1801232ff  mov     rdx, [rsi]; struct IStream *
0x180123302  mov     rcx, [rsp+38h+arg_10]; struct IStream *
0x180123307  call    ?CreateDiagnosticData@@YAJPEAUIStream@@0@Z; CreateDiagnosticData(IStream *,IStream *)
0x18012330c  mov     ebx, eax
0x18012330e  test    eax, eax
0x180123310  jns     short loc_180123319
0x180123312  mov     edx, 37h ; '7'
0x180123317  jmp     short loc_1801232B7
0x180123319  mov     ebx, ebp
0x18012331b  lea     rcx, [rsp+38h+arg_10]
0x180123320  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x180123325  mov     eax, ebx
0x180123327  mov     rbx, [rsp+38h+arg_0]
0x18012332c  mov     rbp, [rsp+38h+arg_8]
0x180123331  add     rsp, 20h
0x180123335  pop     r14
0x180123337  pop     rdi
0x180123338  pop     rsi
0x180123339  retn
```
