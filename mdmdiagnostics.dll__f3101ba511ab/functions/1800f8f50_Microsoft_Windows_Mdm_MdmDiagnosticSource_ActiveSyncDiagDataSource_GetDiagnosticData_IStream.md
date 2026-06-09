# Microsoft::Windows::Mdm::MdmDiagnosticSource::ActiveSyncDiagDataSource::GetDiagnosticData(IStream * *)

- ea: `0x1800f8f50`
- end: `0x1800f9068`
- name: `?GetDiagnosticData@ActiveSyncDiagDataSource@MdmDiagnosticSource@Mdm@Windows@Microsoft@@UEAAJPEAPEAUIStream@@@Z`
- size: `280`
- prototype: `__int64 __fastcall(Microsoft::Windows::Mdm::MdmDiagnosticSource::ActiveSyncDiagDataSource *__hidden this, struct IStream **)`
- caller_count: `0`
- callee_count: `8`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x1800eb1ac`
- `0x1800ed46c`
- `0x1800f8e70`
- `0x1800f8f50`
- `0x1800f92a8`
- `0x1800f962c`
- `0x1800f96c0`
- `0x180123aa8`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x1800f8f91`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x1800f8f91`
- `api-ms-win-shcore-stream-l1-1-0!SHCreateMemStream` at `0x1800f8fe2`
- `api-ms-win-shcore-stream-l1-1-0!SHCreateMemStream` at `0x1800f8fe2`

## string_xrefs

- `0x1800f8fdb`: `<?xml version="1.0" encoding="utf-16"?>\n<DiagData>\n  <DataSource name="ActiveSync">\n    <Key>\n      <Category>ActiveSyncPhoneSettings</Category>\n      <Path>HKUS\S-1-5-21-2702878673-795188819-444038987-2781\Software\Microsoft\ActiveSync\Partners\*</Path>\n      <Representation>EnrollmentID</Representation>\n      <Value>\n        <Name>*</Name>\n        <ValueRepresentation>*</ValueRepresentation>\n      </Value>\n      <Key>\n        <Category>Identifier</Category>\n        <Path>*</Path>\`
- `0x1800f8fca`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\dll\activesyncdiagdata.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall Microsoft::Windows::Mdm::MdmDiagnosticSource::ActiveSyncDiagDataSource::GetDiagnosticData(
        Microsoft::Windows::Mdm::MdmDiagnosticSource::ActiveSyncDiagDataSource *this,
        struct IStream **a2)
{
  HRESULT DiagnosticData; // eax
  unsigned __int64 v5; // rdx
  unsigned int v6; // ebx
  __int64 v7; // rdx
  IStream *v8; // rax
  int v9; // eax
  __int64 v10; // rcx
  UINT cbInit[2]; // [rsp+20h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+18h]
  LPSTREAM ppstm; // [rsp+60h] [rbp+30h] BYREF
  struct IStream *v15; // [rsp+68h] [rbp+38h] BYREF

  v15 = 0;
  ppstm = 0;
  *(_QWORD *)cbInit = 0;
  Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&ppstm);
  DiagnosticData = CreateStreamOnHGlobal(0, 1, &ppstm);
  v6 = DiagnosticData;
  if ( DiagnosticData < 0 )
  {
    v7 = 199;
LABEL_5:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v7,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmdiagnostics\\dll\\activesyncdiagdata.cpp",
      (const char *)(unsigned int)DiagnosticData,
      cbInit[0]);
    goto LABEL_12;
  }
  DiagnosticData = ULongLongMult(0x8E8u, v5, (unsigned __int64 *)cbInit);
  v6 = DiagnosticData;
  if ( DiagnosticData < 0 )
  {
    v7 = 200;
    goto LABEL_5;
  }
  v8 = SHCreateMemStream(
         L"<?xml version=\"1.0\" encoding=\"utf-16\"?>\n"
          "<DiagData>\n"
          "  <DataSource name=\"ActiveSync\">\n"
          "    <Key>\n"
          "      <Category>ActiveSyncPhoneSettings</Category>\n"
          "      <Path>HKUS\\S-1-5-21-2702878673-795188819-444038987-2781\\Software\\Microsoft\\ActiveSync\\Partners\\*</"
          "Path>\n"
          "      <Representation>EnrollmentID</Representation>\n"
          "      <Value>\n"
          "        <Name>*</Name>\n"
          "        <ValueRepresentation>*</ValueRepresentation>\n"
          "      </Value>\n"
          "      <Key>\n"
          "        <Category>Identifier</Category>\n"
          "        <Path>*</Path>\n"
          "        <Representation>ID</Representation>\n"
          "        <Value>\n"
          "          <Name>Enabled</Name>\n"
          "          <ValueRepresentation>Enabled</ValueRepresentation>\n"
          "        </Value>\n"
          "      </Key>\n"
          "    </Key>\n"
          "    <Key>\n"
          "      <Category>ActiveSyncPhonePolicies</Category>\n"
          "      <Path>HKUS\\S-1-5-21-2702878673-795188819-444038987-2781\\Software\\Microsoft\\ActiveSync\\Security\\Pro"
          "vision\\*</Path>\n"
          "      <Representation>PolicyName</Representation>\n"
          "      <Key>\n"
          "        <Category>ConfigSource</Category>\n"
          "        <Path>*</Path>\n"
          "        <Representation>EnrollmentID</Representation>\n"
          "        <Value>\n"
          "          <Name>ApplicationResult</Name>\n"
          "          <ValueRepresentation>ApplicationResult</ValueRepresentation>\n"
          "        </Value>\n"
          "      </Key>\n"
          "    </Key>\n"
          "    <Key>\n"
          "      <Category>ActiveSyncDesktopSettings</Category>\n"
          "      <Path>HKCU\\Software\\Microsoft\\ActiveSync\\Partners\\*</Path>\n"
          "      <Representation>EnrollmentID</Representation>\n"
          "      <Value>\n"
          "        <Name>*</Name>\n"
          "        <ValueRepresentation>*</ValueRepresentation>\n"
          "      </Value>\n"
          "      <Key>\n"
          "        <Category>Identifier</Category>\n"
          "        <Path>*</Path>\n"
          "        <Representation>ID</Representation>\n"
          "        <Value>\n"
          "          <Name>Enabled</Name>\n"
          "          <ValueRepresentation>Enabled</ValueRepresentation>\n"
          "        </Value>\n"
          "      </Key>\n"
          "    </Key>\n"
          "    <Key>\n"
          "      <Category>ActiveSyncDesktopPolicies</Category>\n"
          "      <Path>HKCU\\Software\\Microsoft\\ActiveSync\\Security\\Provision\\*</Path>\n"
          "      <Representation>PolicyName</Representation>\n"
          "      <Key>\n"
          "        <Category>ConfigSource</Category>\n"
          "        <Path>*</Path>\n"
          "        <Representation>EnrollmentID</Representation>\n"
          "        <Value>\n"
          "          <Name>ApplicationResult</Name>\n"
          "          <ValueRepresentation>ApplicationResult</ValueRepresentation>\n"
          "        </Value>\n"
          "      </Key>\n"
          "    </Key>\n"
          "  </DataSource>\n"
          "</DiagData>",
         cbInit[0]);
  Microsoft::WRL::ComPtr<IStream>::operator=(&v15, v8);
  DiagnosticData = CreateDiagnosticData(v15, ppstm);
  v6 = DiagnosticData;
  if ( DiagnosticData < 0 )
  {
    v7 = 205;
    goto LABEL_5;
  }
  v9 = Microsoft::Windows::Mdm::MdmDiagnosticSource::ActiveSyncDiagDataSource::RemovePIIData(this, ppstm, a2);
  v6 = v9;
  if ( v9 >= 0 )
  {
    v6 = 0;
  }
  else if ( (Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits & 8) != 0 )
  {
    McTemplateU0d_EventWriteTransfer(
      v10,
      EnterpriseDiagnosticsMdmDiagnosticsRemovingPIIFromActiveSyncFailure,
      (unsigned int)v9);
  }
LABEL_12:
  Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&ppstm);
  Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&v15);
  return v6;
}

```

## disassembly

```asm
0x1800f8f50  mov     [rsp-18h+arg_0], rbx
0x1800f8f55  push    rbp
0x1800f8f56  push    rsi
0x1800f8f57  push    rdi
0x1800f8f58  mov     rbp, rsp
0x1800f8f5b  sub     rsp, 30h
0x1800f8f5f  mov     rdi, rdx
0x1800f8f62  mov     rsi, rcx
0x1800f8f65  mov     [rbp+arg_18], 0
0x1800f8f6d  mov     [rbp+ppstm], 0
0x1800f8f75  mov     qword ptr [rbp+cbInit], 0
0x1800f8f7d  lea     rcx, [rbp+ppstm]
0x1800f8f81  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x1800f8f86  lea     r8, [rbp+ppstm]; ppstm
0x1800f8f8a  mov     edx, 1; fDeleteOnRelease
0x1800f8f8f  xor     ecx, ecx; hGlobal
0x1800f8f91  call    cs:__imp_CreateStreamOnHGlobal
0x1800f8f98  nop     dword ptr [rax+rax+00h]
0x1800f8f9d  mov     ebx, eax
0x1800f8f9f  test    eax, eax
0x1800f8fa1  jns     short loc_1800F8FAA
0x1800f8fa3  mov     edx, 0C7h
0x1800f8fa8  jmp     short loc_1800F8FC3
0x1800f8faa  lea     r8, [rbp+cbInit]; unsigned __int64 *
0x1800f8fae  mov     ecx, 8E8h; unsigned __int64
0x1800f8fb3  call    ?ULongLongMult@@YAJ_K0PEA_K@Z; ULongLongMult(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x1800f8fb8  mov     ebx, eax
0x1800f8fba  test    eax, eax
0x1800f8fbc  jns     short loc_1800F8FD8
0x1800f8fbe  mov     edx, 0C8h; void *
0x1800f8fc3  mov     rcx, [rbp+18h]; this
0x1800f8fc7  mov     r9d, eax; char *
0x1800f8fca  lea     r8, aOnecoreuapAdmi_31; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x1800f8fd1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800f8fd6  jmp     short loc_1800F9045
0x1800f8fd8  mov     edx, [rbp+cbInit]; cbInit
0x1800f8fdb  lea     rcx, pInit; "<?xml version=\"1.0\" encoding=\"utf-16"...
0x1800f8fe2  call    cs:__imp_SHCreateMemStream
0x1800f8fe9  nop     dword ptr [rax+rax+00h]
0x1800f8fee  mov     rdx, rax
0x1800f8ff1  lea     rcx, [rbp+arg_18]
0x1800f8ff5  call    ??4?$ComPtr@UIStream@@@WRL@Microsoft@@QEAAAEAV012@PEAUIStream@@@Z; Microsoft::WRL::ComPtr<IStream>::operator=(IStream *)
0x1800f8ffa  mov     rdx, [rbp+ppstm]; struct IStream *
0x1800f8ffe  mov     rcx, [rbp+arg_18]; struct IStream *
0x1800f9002  call    ?CreateDiagnosticData@@YAJPEAUIStream@@0@Z; CreateDiagnosticData(IStream *,IStream *)
0x1800f9007  mov     ebx, eax
0x1800f9009  test    eax, eax
0x1800f900b  jns     short loc_1800F9014
0x1800f900d  mov     edx, 0CDh
0x1800f9012  jmp     short loc_1800F8FC3
0x1800f9014  mov     r8, rdi; struct IStream **
0x1800f9017  mov     rdx, [rbp+ppstm]; struct IStream *
0x1800f901b  mov     rcx, rsi; this
0x1800f901e  call    ?RemovePIIData@ActiveSyncDiagDataSource@MdmDiagnosticSource@Mdm@Windows@Microsoft@@AEAAJPEAUIStream@@PEAPEAU6@@Z; Microsoft::Windows::Mdm::MdmDiagnosticSource::ActiveSyncDiagDataSource::RemovePIIData(IStream *,IStream * *)
0x1800f9023  mov     ebx, eax
0x1800f9025  test    eax, eax
0x1800f9027  jns     short loc_1800F9043
0x1800f9029  test    cs:Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits, 8
0x1800f9030  jz      short loc_1800F9045
0x1800f9032  mov     r8d, eax
0x1800f9035  lea     rdx, EnterpriseDiagnosticsMdmDiagnosticsRemovingPIIFromActiveSyncFailure
0x1800f903c  call    McTemplateU0d_EventWriteTransfer
0x1800f9041  jmp     short loc_1800F9045
0x1800f9043  xor     ebx, ebx
0x1800f9045  lea     rcx, [rbp+ppstm]
0x1800f9049  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x1800f904e  nop
0x1800f904f  lea     rcx, [rbp+arg_18]
0x1800f9053  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x1800f9058  mov     eax, ebx
0x1800f905a  mov     rbx, [rsp+30h+arg_0]
0x1800f905f  add     rsp, 30h
0x1800f9063  pop     rdi
0x1800f9064  pop     rsi
0x1800f9065  pop     rbp
0x1800f9066  retn
```
