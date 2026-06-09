# Microsoft::Windows::Mdm::MdmDiagnosticSource::EnterpriseDesktopAppManagementDiagDataSource::GetDiagnosticData(IStream * *)

- ea: `0x180105c40`
- end: `0x180105d4b`
- name: `?GetDiagnosticData@EnterpriseDesktopAppManagementDiagDataSource@MdmDiagnosticSource@Mdm@Windows@Microsoft@@UEAAJPEAPEAUIStream@@@Z`
- size: `267`
- prototype: `int(Microsoft::Windows::Mdm::MdmDiagnosticSource::EnterpriseDesktopAppManagementDiagDataSource *__hidden this, struct IStream **)`
- caller_count: `0`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callees

- `0x1800eb1ac`
- `0x1800ed46c`
- `0x1800f8e70`
- `0x1800f962c`
- `0x180105c40`
- `0x180123aa8`

## import_xrefs

- `ntdll!RtlIsStateSeparationEnabled` at `0x180105c7f`
- `ntdll!RtlIsStateSeparationEnabled` at `0x180105cdd`
- `ntdll!RtlIsStateSeparationEnabled` at `0x180105c7f`
- `ntdll!RtlIsStateSeparationEnabled` at `0x180105cdd`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x180105c68`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x180105c68`
- `api-ms-win-shcore-stream-l1-1-0!SHCreateMemStream` at `0x180105cf6`
- `api-ms-win-shcore-stream-l1-1-0!SHCreateMemStream` at `0x180105cf6`

## string_xrefs

- `0x180105c92`: `<?xml version="1.0" encoding="utf-16"?>\n        <DiagData>\n          <DataSource name="OSDataEnterpriseDesktopAppManagementinfo">\n            <key>\n              <Category>MsiInstallations</Category>\n              <Path>HKLM\OSData\Software\Microsoft\EnterpriseDesktopAppManagement</Path>\n              <key>\n                <Category>TargetedUser</Category>\n                <Path>*</Path>\n                <Representation>UserSid</Representation>\n                <key>\n                  <C`
- `0x180105c8b`: `<?xml version="1.0" encoding="utf-16"?>\n        <DiagData>\n          <DataSource name="EnterpriseDesktopAppManagementinfo">\n            <key>\n              <Category>MsiInstallations</Category>\n              <Path>HKLM\Software\Microsoft\EnterpriseDesktopAppManagement</Path>\n              <key>\n                <Category>TargetedUser</Category>\n                <Path>*</Path>\n                <Representation>UserSid</Representation>\n                <key>\n                  <Category>Packa`
- `0x180105ccf`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\dll\enterprisedesktopappmanagementdiagdata.cpp`

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
0x180105c40  mov     rax, rsp
0x180105c43  mov     [rax+8], rbx
0x180105c47  mov     [rax+10h], rbp
0x180105c4b  push    rsi
0x180105c4c  push    rdi
0x180105c4d  push    r14; int
0x180105c4f  sub     rsp, 20h
0x180105c53  mov     rsi, rdx
0x180105c56  xor     ebp, ebp
0x180105c58  mov     [rax+18h], rbp
0x180105c5c  mov     [rax+20h], rbp
0x180105c60  mov     r8, rdx; ppstm
0x180105c63  lea     edx, [rbp+1]; fDeleteOnRelease
0x180105c66  xor     ecx, ecx; hGlobal
0x180105c68  call    cs:__imp_CreateStreamOnHGlobal
0x180105c6f  nop     dword ptr [rax+rax+00h]
0x180105c74  mov     ebx, eax
0x180105c76  test    eax, eax
0x180105c78  jns     short loc_180105C7F
0x180105c7a  lea     edx, [rbp+26h]
0x180105c7d  jmp     short loc_180105CC7
0x180105c7f  call    cs:__imp_RtlIsStateSeparationEnabled
0x180105c86  nop     dword ptr [rax+rax+00h]
0x180105c8b  lea     r14, aXmlVersion10En_19; "<?xml version=\"1.0\" encoding=\"utf-16"...
0x180105c92  lea     rdi, aXmlVersion10En_22; "<?xml version=\"1.0\" encoding=\"utf-16"...
0x180105c99  mov     rdx, rdi
0x180105c9c  test    al, al
0x180105c9e  cmovz   rdx, r14; unsigned __int64
0x180105ca2  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180105ca6  inc     rcx
0x180105ca9  cmp     [rdx+rcx*2], bp
0x180105cad  jnz     short loc_180105CA6
0x180105caf  inc     rcx; unsigned __int64
0x180105cb2  lea     r8, [rsp+38h+cbInit]; unsigned __int64 *
0x180105cb7  call    ?ULongLongMult@@YAJ_K0PEA_K@Z; ULongLongMult(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x180105cbc  mov     ebx, eax
0x180105cbe  test    eax, eax
0x180105cc0  jns     short loc_180105CDD
0x180105cc2  mov     edx, 27h ; '''; void *
0x180105cc7  mov     rcx, [rsp+38h]; this
0x180105ccc  mov     r9d, eax; char *
0x180105ccf  lea     r8, aOnecoreuapAdmi_2; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x180105cd6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180105cdb  jmp     short loc_180105D2B
0x180105cdd  call    cs:__imp_RtlIsStateSeparationEnabled
0x180105ce4  nop     dword ptr [rax+rax+00h]
0x180105ce9  test    al, al
0x180105ceb  cmovz   rdi, r14
0x180105cef  mov     edx, dword ptr [rsp+38h+cbInit]; cbInit
0x180105cf3  mov     rcx, rdi; pInit
0x180105cf6  call    cs:__imp_SHCreateMemStream
0x180105cfd  nop     dword ptr [rax+rax+00h]
0x180105d02  mov     rdx, rax
0x180105d05  lea     rcx, [rsp+38h+arg_10]
0x180105d0a  call    ??4?$ComPtr@UIStream@@@WRL@Microsoft@@QEAAAEAV012@PEAUIStream@@@Z; Microsoft::WRL::ComPtr<IStream>::operator=(IStream *)
0x180105d0f  mov     rdx, [rsi]; struct IStream *
0x180105d12  mov     rcx, [rsp+38h+arg_10]; struct IStream *
0x180105d17  call    ?CreateDiagnosticData@@YAJPEAUIStream@@0@Z; CreateDiagnosticData(IStream *,IStream *)
0x180105d1c  mov     ebx, eax
0x180105d1e  test    eax, eax
0x180105d20  jns     short loc_180105D29
0x180105d22  mov     edx, 2Bh ; '+'
0x180105d27  jmp     short loc_180105CC7
0x180105d29  mov     ebx, ebp
0x180105d2b  lea     rcx, [rsp+38h+arg_10]
0x180105d30  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x180105d35  mov     eax, ebx
0x180105d37  mov     rbx, [rsp+38h+arg_0]
0x180105d3c  mov     rbp, [rsp+38h+arg_8]
0x180105d41  add     rsp, 20h
0x180105d45  pop     r14
0x180105d47  pop     rdi
0x180105d48  pop     rsi
0x180105d49  retn
```
