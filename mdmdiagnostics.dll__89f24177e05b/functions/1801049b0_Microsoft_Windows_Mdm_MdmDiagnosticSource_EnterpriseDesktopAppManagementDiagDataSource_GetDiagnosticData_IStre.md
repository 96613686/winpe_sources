# Microsoft::Windows::Mdm::MdmDiagnosticSource::EnterpriseDesktopAppManagementDiagDataSource::GetDiagnosticData(IStream * *)

- ea: `0x1801049b0`
- end: `0x180104aa2`
- name: `?GetDiagnosticData@EnterpriseDesktopAppManagementDiagDataSource@MdmDiagnosticSource@Mdm@Windows@Microsoft@@UEAAJPEAPEAUIStream@@@Z`
- size: `242`
- prototype: `int(Microsoft::Windows::Mdm::MdmDiagnosticSource::EnterpriseDesktopAppManagementDiagDataSource *__hidden this, struct IStream **)`
- caller_count: `0`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callees

- `0x1800ead14`
- `0x1800ece5c`
- `0x1800f7f10`
- `0x1800f8680`
- `0x1801049b0`
- `0x180122018`

## import_xrefs

- `ntdll!RtlIsStateSeparationEnabled` at `0x1801049e9`
- `ntdll!RtlIsStateSeparationEnabled` at `0x180104a41`
- `ntdll!RtlIsStateSeparationEnabled` at `0x1801049e9`
- `ntdll!RtlIsStateSeparationEnabled` at `0x180104a41`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x1801049d8`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x1801049d8`
- `api-ms-win-shcore-stream-l1-1-0!SHCreateMemStream` at `0x180104a54`
- `api-ms-win-shcore-stream-l1-1-0!SHCreateMemStream` at `0x180104a54`

## string_xrefs

- `0x1801049ef`: `<?xml version="1.0" encoding="utf-16"?>\n        <DiagData>\n          <DataSource name="EnterpriseDesktopAppManagementinfo">\n            <key>\n              <Category>MsiInstallations</Category>\n              <Path>HKLM\Software\Microsoft\EnterpriseDesktopAppManagement</Path>\n              <key>\n                <Category>TargetedUser</Category>\n                <Path>*</Path>\n                <Representation>UserSid</Representation>\n                <key>\n                  <Category>Packa`
- `0x1801049f6`: `<?xml version="1.0" encoding="utf-16"?>\n        <DiagData>\n          <DataSource name="OSDataEnterpriseDesktopAppManagementinfo">\n            <key>\n              <Category>MsiInstallations</Category>\n              <Path>HKLM\OSData\Software\Microsoft\EnterpriseDesktopAppManagement</Path>\n              <key>\n                <Category>TargetedUser</Category>\n                <Path>*</Path>\n                <Representation>UserSid</Representation>\n                <key>\n                  <C`
- `0x180104a33`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\dll\enterprisedesktopappmanagementdiagdata.cpp`

## pseudocode

```c
__int64 __fastcall Microsoft::Windows::Mdm::MdmDiagnosticSource::EnterpriseDesktopAppManagementDiagDataSource::GetDiagnosticData(
        Microsoft::Windows::Mdm::MdmDiagnosticSource::EnterpriseDesktopAppManagementDiagDataSource *this,
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
                        "        <DiagData>\n"
                        "          <DataSource name=\"OSDataEnterpriseDesktopAppManagementinfo\">\n"
                        "            <key>\n"
                        "              <Category>MsiInstallations</Category>\n"
                        "              <Path>HKLM\\OSData\\Software\\Microsoft\\EnterpriseDesktopAppManagement</Path>\n"
                        "              <key>\n"
                        "                <Category>TargetedUser</Category>\n"
                        "                <Path>*</Path>\n"
                        "                <Representation>UserSid</Representation>\n"
                        "                <key>\n"
                        "                  <Category>Package</Category>\n"
                        "                  <Path>*</Path>\n"
                        "                  <Representation>Type</Representation>\n"
                        "                  <key>\n"
                        "                    <Category>Details</Category>\n"
                        "                    <Path>*</Path>\n"
                        "                    <Representation>PackageId</Representation>\n"
                        "                    <Value>\n"
                        "                      <Name>*</Name>\n"
                        "                      <ValueRepresentation>*</ValueRepresentation>\n"
                        "                    </Value>\n"
                        "                  </key>\n"
                        "                </key>\n"
                        "              </key>\n"
                        "            </key>\n"
                        "          </DataSource>\n"
                        "        </DiagData>";
    v8 = L"<?xml version=\"1.0\" encoding=\"utf-16\"?>\n"
          "        <DiagData>\n"
          "          <DataSource name=\"OSDataEnterpriseDesktopAppManagementinfo\">\n"
          "            <key>\n"
          "              <Category>MsiInstallations</Category>\n"
          "              <Path>HKLM\\OSData\\Software\\Microsoft\\EnterpriseDesktopAppManagement</Path>\n"
          "              <key>\n"
          "                <Category>TargetedUser</Category>\n"
          "                <Path>*</Path>\n"
          "                <Representation>UserSid</Representation>\n"
          "                <key>\n"
          "                  <Category>Package</Category>\n"
          "                  <Path>*</Path>\n"
          "                  <Representation>Type</Representation>\n"
          "                  <key>\n"
          "                    <Category>Details</Category>\n"
          "                    <Path>*</Path>\n"
          "                    <Representation>PackageId</Representation>\n"
          "                    <Value>\n"
          "                      <Name>*</Name>\n"
          "                      <ValueRepresentation>*</ValueRepresentation>\n"
          "                    </Value>\n"
          "                  </key>\n"
          "                </key>\n"
          "              </key>\n"
          "            </key>\n"
          "          </DataSource>\n"
          "        </DiagData>";
    if ( !IsStateSeparationEnabled )
      v8 = (const wchar_t *)L"<?xml version=\"1.0\" encoding=\"utf-16\"?>\n"
                             "        <DiagData>\n"
                             "          <DataSource name=\"EnterpriseDesktopAppManagementinfo\">\n"
                             "            <key>\n"
                             "              <Category>MsiInstallations</Category>\n"
                             "              <Path>HKLM\\Software\\Microsoft\\EnterpriseDesktopAppManagement</Path>\n"
                             "              <key>\n"
                             "                <Category>TargetedUser</Category>\n"
                             "                <Path>*</Path>\n"
                             "                <Representation>UserSid</Representation>\n"
                             "                <key>\n"
                             "                  <Category>Package</Category>\n"
                             "                  <Path>*</Path>\n"
                             "                  <Representation>Type</Representation>\n"
                             "                  <key>\n"
                             "                    <Category>Details</Category>\n"
                             "                    <Path>*</Path>\n"
                             "                    <Representation>PackageId</Representation>\n"
                             "                    <Value>\n"
                             "                      <Name>*</Name>\n"
                             "                      <ValueRepresentation>*</ValueRepresentation>\n"
                             "                    </Value>\n"
                             "                  </key>\n"
                             "                </key>\n"
                             "              </key>\n"
                             "            </key>\n"
                             "          </DataSource>\n"
                             "        </DiagData>";
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
              "        <DiagData>\n"
              "          <DataSource name=\"EnterpriseDesktopAppManagementinfo\">\n"
              "            <key>\n"
              "              <Category>MsiInstallations</Category>\n"
              "              <Path>HKLM\\Software\\Microsoft\\EnterpriseDesktopAppManagement</Path>\n"
              "              <key>\n"
              "                <Category>TargetedUser</Category>\n"
              "                <Path>*</Path>\n"
              "                <Representation>UserSid</Representation>\n"
              "                <key>\n"
              "                  <Category>Package</Category>\n"
              "                  <Path>*</Path>\n"
              "                  <Representation>Type</Representation>\n"
              "                  <key>\n"
              "                    <Category>Details</Category>\n"
              "                    <Path>*</Path>\n"
              "                    <Representation>PackageId</Representation>\n"
              "                    <Value>\n"
              "                      <Name>*</Name>\n"
              "                      <ValueRepresentation>*</ValueRepresentation>\n"
              "                    </Value>\n"
              "                  </key>\n"
              "                </key>\n"
              "              </key>\n"
              "            </key>\n"
              "          </DataSource>\n"
              "        </DiagData>";
      v10 = SHCreateMemStream(v7, cbInit);
      Microsoft::WRL::ComPtr<IStream>::operator=(&v14, v10);
      StreamOnHGlobal = CreateDiagnosticData(v14, *a2);
      v4 = StreamOnHGlobal;
      if ( StreamOnHGlobal >= 0 )
      {
        v4 = 0;
        goto LABEL_15;
      }
      v5 = 43;
    }
    else
    {
      v5 = 39;
    }
  }
  else
  {
    v5 = 38;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v5,
    (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmdiagnostics\\dll\\enterprisedesktopappmanagementdiagdata.cpp",
    (const char *)(unsigned int)StreamOnHGlobal,
    v12);
LABEL_15:
  Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&v14);
  return v4;
}

```

## disassembly

```asm
0x1801049b0  mov     rax, rsp
0x1801049b3  mov     [rax+8], rbx
0x1801049b7  mov     [rax+10h], rbp
0x1801049bb  push    rsi
0x1801049bc  push    rdi
0x1801049bd  push    r14; int
0x1801049bf  sub     rsp, 20h
0x1801049c3  mov     rsi, rdx
0x1801049c6  xor     ebp, ebp
0x1801049c8  mov     [rax+18h], rbp
0x1801049cc  mov     [rax+20h], rbp
0x1801049d0  mov     r8, rdx; ppstm
0x1801049d3  lea     edx, [rbp+1]; fDeleteOnRelease
0x1801049d6  xor     ecx, ecx; hGlobal
0x1801049d8  call    cs:__imp_CreateStreamOnHGlobal
0x1801049de  mov     ebx, eax
0x1801049e0  test    eax, eax
0x1801049e2  jns     short loc_1801049E9
0x1801049e4  lea     edx, [rbp+26h]
0x1801049e7  jmp     short loc_180104A2B
0x1801049e9  call    cs:__imp_RtlIsStateSeparationEnabled
0x1801049ef  lea     r14, aXmlVersion10En_19; "<?xml version=\"1.0\" encoding=\"utf-16"...
0x1801049f6  lea     rdi, aXmlVersion10En_22; "<?xml version=\"1.0\" encoding=\"utf-16"...
0x1801049fd  mov     rdx, rdi
0x180104a00  test    al, al
0x180104a02  cmovz   rdx, r14; unsigned __int64
0x180104a06  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180104a0a  inc     rcx
0x180104a0d  cmp     [rdx+rcx*2], bp
0x180104a11  jnz     short loc_180104A0A
0x180104a13  inc     rcx; unsigned __int64
0x180104a16  lea     r8, [rsp+38h+cbInit]; unsigned __int64 *
0x180104a1b  call    ?ULongLongMult@@YAJ_K0PEA_K@Z; ULongLongMult(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x180104a20  mov     ebx, eax
0x180104a22  test    eax, eax
0x180104a24  jns     short loc_180104A41
0x180104a26  mov     edx, 27h ; '''; void *
0x180104a2b  mov     rcx, [rsp+38h]; this
0x180104a30  mov     r9d, eax; char *
0x180104a33  lea     r8, aOnecoreuapAdmi_2; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x180104a3a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180104a3f  jmp     short loc_180104A83
0x180104a41  call    cs:__imp_RtlIsStateSeparationEnabled
0x180104a47  test    al, al
0x180104a49  cmovz   rdi, r14
0x180104a4d  mov     edx, dword ptr [rsp+38h+cbInit]; cbInit
0x180104a51  mov     rcx, rdi; pInit
0x180104a54  call    cs:__imp_SHCreateMemStream
0x180104a5a  mov     rdx, rax
0x180104a5d  lea     rcx, [rsp+38h+arg_10]
0x180104a62  call    ??4?$ComPtr@UIStream@@@WRL@Microsoft@@QEAAAEAV012@PEAUIStream@@@Z; Microsoft::WRL::ComPtr<IStream>::operator=(IStream *)
0x180104a67  mov     rdx, [rsi]; struct IStream *
0x180104a6a  mov     rcx, [rsp+38h+arg_10]; struct IStream *
0x180104a6f  call    ?CreateDiagnosticData@@YAJPEAUIStream@@0@Z; CreateDiagnosticData(IStream *,IStream *)
0x180104a74  mov     ebx, eax
0x180104a76  test    eax, eax
0x180104a78  jns     short loc_180104A81
0x180104a7a  mov     edx, 2Bh ; '+'
0x180104a7f  jmp     short loc_180104A2B
0x180104a81  mov     ebx, ebp
0x180104a83  lea     rcx, [rsp+38h+arg_10]
0x180104a88  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x180104a8d  mov     eax, ebx
0x180104a8f  mov     rbx, [rsp+38h+arg_0]
0x180104a94  mov     rbp, [rsp+38h+arg_8]
0x180104a99  add     rsp, 20h
0x180104a9d  pop     r14
0x180104a9f  pop     rdi
0x180104aa0  pop     rsi
0x180104aa1  retn
```
