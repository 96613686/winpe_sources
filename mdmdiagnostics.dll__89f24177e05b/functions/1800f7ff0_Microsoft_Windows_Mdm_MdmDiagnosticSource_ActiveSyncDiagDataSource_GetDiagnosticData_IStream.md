# Microsoft::Windows::Mdm::MdmDiagnosticSource::ActiveSyncDiagDataSource::GetDiagnosticData(IStream * *)

- ea: `0x1800f7ff0`
- end: `0x1800f80fb`
- name: `?GetDiagnosticData@ActiveSyncDiagDataSource@MdmDiagnosticSource@Mdm@Windows@Microsoft@@UEAAJPEAPEAUIStream@@@Z`
- size: `267`
- prototype: `__int64 __fastcall(Microsoft::Windows::Mdm::MdmDiagnosticSource::ActiveSyncDiagDataSource *__hidden this, struct IStream **)`
- caller_count: `0`
- callee_count: `8`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x1800ead14`
- `0x1800ece5c`
- `0x1800f7f10`
- `0x1800f7ff0`
- `0x1800f8310`
- `0x1800f8680`
- `0x1800f8708`
- `0x180122018`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x1800f8031`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x1800f8031`
- `api-ms-win-shcore-stream-l1-1-0!SHCreateMemStream` at `0x1800f807c`
- `api-ms-win-shcore-stream-l1-1-0!SHCreateMemStream` at `0x1800f807c`

## string_xrefs

- `0x1800f8075`: `<?xml version="1.0" encoding="utf-16"?>\n<DiagData>\n  <DataSource name="ActiveSync">\n    <Key>\n      <Category>ActiveSyncPhoneSettings</Category>\n      <Path>HKUS\S-1-5-21-2702878673-795188819-444038987-2781\Software\Microsoft\ActiveSync\Partners\*</Path>\n      <Representation>EnrollmentID</Representation>\n      <Value>\n        <Name>*</Name>\n        <ValueRepresentation>*</ValueRepresentation>\n      </Value>\n      <Key>\n        <Category>Identifier</Category>\n        <Path>*</Path>\`
- `0x1800f8064`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\dll\activesyncdiagdata.cpp`

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
0x1800f7ff0  mov     [rsp-18h+arg_0], rbx
0x1800f7ff5  push    rbp
0x1800f7ff6  push    rsi
0x1800f7ff7  push    rdi
0x1800f7ff8  mov     rbp, rsp
0x1800f7ffb  sub     rsp, 30h
0x1800f7fff  mov     rdi, rdx
0x1800f8002  mov     rsi, rcx
0x1800f8005  mov     [rbp+arg_18], 0
0x1800f800d  mov     [rbp+ppstm], 0
0x1800f8015  mov     qword ptr [rbp+cbInit], 0
0x1800f801d  lea     rcx, [rbp+ppstm]
0x1800f8021  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x1800f8026  lea     r8, [rbp+ppstm]; ppstm
0x1800f802a  mov     edx, 1; fDeleteOnRelease
0x1800f802f  xor     ecx, ecx; hGlobal
0x1800f8031  call    cs:__imp_CreateStreamOnHGlobal
0x1800f8037  mov     ebx, eax
0x1800f8039  test    eax, eax
0x1800f803b  jns     short loc_1800F8044
0x1800f803d  mov     edx, 0C7h
0x1800f8042  jmp     short loc_1800F805D
0x1800f8044  lea     r8, [rbp+cbInit]; unsigned __int64 *
0x1800f8048  mov     ecx, 8E8h; unsigned __int64
0x1800f804d  call    ?ULongLongMult@@YAJ_K0PEA_K@Z; ULongLongMult(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x1800f8052  mov     ebx, eax
0x1800f8054  test    eax, eax
0x1800f8056  jns     short loc_1800F8072
0x1800f8058  mov     edx, 0C8h; void *
0x1800f805d  mov     rcx, [rbp+18h]; this
0x1800f8061  mov     r9d, eax; char *
0x1800f8064  lea     r8, aOnecoreuapAdmi_31; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x1800f806b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800f8070  jmp     short loc_1800F80D9
0x1800f8072  mov     edx, [rbp+cbInit]; cbInit
0x1800f8075  lea     rcx, pInit; "<?xml version=\"1.0\" encoding=\"utf-16"...
0x1800f807c  call    cs:__imp_SHCreateMemStream
0x1800f8082  mov     rdx, rax
0x1800f8085  lea     rcx, [rbp+arg_18]
0x1800f8089  call    ??4?$ComPtr@UIStream@@@WRL@Microsoft@@QEAAAEAV012@PEAUIStream@@@Z; Microsoft::WRL::ComPtr<IStream>::operator=(IStream *)
0x1800f808e  mov     rdx, [rbp+ppstm]; struct IStream *
0x1800f8092  mov     rcx, [rbp+arg_18]; struct IStream *
0x1800f8096  call    ?CreateDiagnosticData@@YAJPEAUIStream@@0@Z; CreateDiagnosticData(IStream *,IStream *)
0x1800f809b  mov     ebx, eax
0x1800f809d  test    eax, eax
0x1800f809f  jns     short loc_1800F80A8
0x1800f80a1  mov     edx, 0CDh
0x1800f80a6  jmp     short loc_1800F805D
0x1800f80a8  mov     r8, rdi; struct IStream **
0x1800f80ab  mov     rdx, [rbp+ppstm]; struct IStream *
0x1800f80af  mov     rcx, rsi; this
0x1800f80b2  call    ?RemovePIIData@ActiveSyncDiagDataSource@MdmDiagnosticSource@Mdm@Windows@Microsoft@@AEAAJPEAUIStream@@PEAPEAU6@@Z; Microsoft::Windows::Mdm::MdmDiagnosticSource::ActiveSyncDiagDataSource::RemovePIIData(IStream *,IStream * *)
0x1800f80b7  mov     ebx, eax
0x1800f80b9  test    eax, eax
0x1800f80bb  jns     short loc_1800F80D7
0x1800f80bd  test    cs:Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits, 8
0x1800f80c4  jz      short loc_1800F80D9
0x1800f80c6  mov     r8d, eax
0x1800f80c9  lea     rdx, EnterpriseDiagnosticsMdmDiagnosticsRemovingPIIFromActiveSyncFailure
0x1800f80d0  call    McTemplateU0d_EventWriteTransfer
0x1800f80d5  jmp     short loc_1800F80D9
0x1800f80d7  xor     ebx, ebx
0x1800f80d9  lea     rcx, [rbp+ppstm]
0x1800f80dd  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x1800f80e2  nop
0x1800f80e3  lea     rcx, [rbp+arg_18]
0x1800f80e7  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x1800f80ec  mov     eax, ebx
0x1800f80ee  mov     rbx, [rsp+30h+arg_0]
0x1800f80f3  add     rsp, 30h
0x1800f80f7  pop     rdi
0x1800f80f8  pop     rsi
0x1800f80f9  pop     rbp
0x1800f80fa  retn
```
