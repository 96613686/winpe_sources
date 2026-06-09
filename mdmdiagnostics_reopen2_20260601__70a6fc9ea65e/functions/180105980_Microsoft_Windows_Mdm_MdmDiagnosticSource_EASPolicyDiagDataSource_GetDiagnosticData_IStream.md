# Microsoft::Windows::Mdm::MdmDiagnosticSource::EASPolicyDiagDataSource::GetDiagnosticData(IStream * *)

- ea: `0x180105980`
- end: `0x180105a8b`
- name: `?GetDiagnosticData@EASPolicyDiagDataSource@MdmDiagnosticSource@Mdm@Windows@Microsoft@@UEAAJPEAPEAUIStream@@@Z`
- size: `267`
- prototype: `int(Microsoft::Windows::Mdm::MdmDiagnosticSource::EASPolicyDiagDataSource *__hidden this, struct IStream **)`
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x1800eb1ac`
- `0x1800ed46c`
- `0x1800f8e70`
- `0x1800f962c`
- `0x180105980`
- `0x180123aa8`

## import_xrefs

- `ntdll!RtlIsStateSeparationEnabled` at `0x1801059bf`
- `ntdll!RtlIsStateSeparationEnabled` at `0x180105a1d`
- `ntdll!RtlIsStateSeparationEnabled` at `0x1801059bf`
- `ntdll!RtlIsStateSeparationEnabled` at `0x180105a1d`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x1801059a8`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x1801059a8`
- `api-ms-win-shcore-stream-l1-1-0!SHCreateMemStream` at `0x180105a36`
- `api-ms-win-shcore-stream-l1-1-0!SHCreateMemStream` at `0x180105a36`

## string_xrefs

- `0x1801059cb`: `<?xml version="1.0" encoding="utf-16"?>\n<DiagData>\n  <DataSource name="EAS">\n    <Key>\n      <Category>EASPolicies</Category>\n      <Path>HKLM\System\CurrentControlSet\Control\Eas\*</Path>\n      <Representation>Type</Representation>\n      <Value>\n        <Name>1</Name>\n        <ValueRepresentation>MinDevicePasswordComplexCharacters</ValueRepresentation>\n      </Value>\n      <Value>\n        <Name>2</Name>\n        <ValueRepresentation>MinDevicePasswordLength</ValueRepresentation>\n   `
- `0x1801059d2`: `<?xml version="1.0" encoding="utf-16"?>\n<DiagData>\n  <DataSource name="OSDataEAS">\n    <Key>\n      <Category>EASPolicies</Category>\n      <Path>HKLM\OSData\System\CurrentControlSet\Control\Eas\*</Path>\n      <Representation>Type</Representation>\n      <Value>\n        <Name>1</Name>\n        <ValueRepresentation>MinDevicePasswordComplexCharacters</ValueRepresentation>\n      </Value>\n      <Value>\n        <Name>2</Name>\n        <ValueRepresentation>MinDevicePasswordLength</ValueReprese`
- `0x180105a0f`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\dll\easpolicydiagdata.cpp`

## pseudocode

```c
__int64 __fastcall Microsoft::Windows::Mdm::MdmDiagnosticSource::EASPolicyDiagDataSource::GetDiagnosticData(
        Microsoft::Windows::Mdm::MdmDiagnosticSource::EASPolicyDiagDataSource *this,
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
                        "  <DataSource name=\"OSDataEAS\">\n"
                        "    <Key>\n"
                        "      <Category>EASPolicies</Category>\n"
                        "      <Path>HKLM\\OSData\\System\\CurrentControlSet\\Control\\Eas\\*</Path>\n"
                        "      <Representation>Type</Representation>\n"
                        "      <Value>\n"
                        "        <Name>1</Name>\n"
                        "        <ValueRepresentation>MinDevicePasswordComplexCharacters</ValueRepresentation>\n"
                        "      </Value>\n"
                        "      <Value>\n"
                        "        <Name>2</Name>\n"
                        "        <ValueRepresentation>MinDevicePasswordLength</ValueRepresentation>\n"
                        "      </Value>\n"
                        "      <Value>\n"
                        "        <Name>3</Name>\n"
                        "        <ValueRepresentation>DevicePasswordExpiration</ValueRepresentation>\n"
                        "      </Value>\n"
                        "      <Value>\n"
                        "        <Name>4</Name>\n"
                        "        <ValueRepresentation>DevicePasswordHistory</ValueRepresentation>\n"
                        "      </Value>\n"
                        "      <Value>\n"
                        "        <Name>5</Name>\n"
                        "        <ValueRepresentation>AllowSimpleDevicePassword</ValueRepresentation>\n"
                        "      </Value>\n"
                        "      <Value>\n"
                        "        <Name>6</Name>\n"
                        "        <ValueRepresentation>MaxDevicePasswordFailedAttempts</ValueRepresentation>\n"
                        "      </Value>\n"
                        "      <Value>\n"
                        "        <Name>7</Name>\n"
                        "        <ValueRepresentation>MaxInactivityTimeDeviceLock</ValueRepresentation>\n"
                        "      </Value>\n"
                        "      <Value>\n"
                        "        <Name>8</Name>\n"
                        "        <ValueRepresentation>RequireDeviceEncryption</ValueRepresentation>\n"
                        "      </Value>\n"
                        "      <Key>\n"
                        "        <Category>PolicySource</Category>\n"
                        "        <Path>*</Path>\n"
                        "        <Representation>Source</Representation>\n"
                        "      </Key>\n"
                        "    </Key>\n"
                        "  </DataSource>\n"
                        "</DiagData>";
    v8 = L"<?xml version=\"1.0\" encoding=\"utf-16\"?>\n"
          "<DiagData>\n"
          "  <DataSource name=\"OSDataEAS\">\n"
          "    <Key>\n"
          "      <Category>EASPolicies</Category>\n"
          "      <Path>HKLM\\OSData\\System\\CurrentControlSet\\Control\\Eas\\*</Path>\n"
          "      <Representation>Type</Representation>\n"
          "      <Value>\n"
          "        <Name>1</Name>\n"
          "        <ValueRepresentation>MinDevicePasswordComplexCharacters</ValueRepresentation>\n"
          "      </Value>\n"
          "      <Value>\n"
          "        <Name>2</Name>\n"
          "        <ValueRepresentation>MinDevicePasswordLength</ValueRepresentation>\n"
          "      </Value>\n"
          "      <Value>\n"
          "        <Name>3</Name>\n"
          "        <ValueRepresentation>DevicePasswordExpiration</ValueRepresentation>\n"
          "      </Value>\n"
          "      <Value>\n"
          "        <Name>4</Name>\n"
          "        <ValueRepresentation>DevicePasswordHistory</ValueRepresentation>\n"
          "      </Value>\n"
          "      <Value>\n"
          "        <Name>5</Name>\n"
          "        <ValueRepresentation>AllowSimpleDevicePassword</ValueRepresentation>\n"
          "      </Value>\n"
          "      <Value>\n"
          "        <Name>6</Name>\n"
          "        <ValueRepresentation>MaxDevicePasswordFailedAttempts</ValueRepresentation>\n"
          "      </Value>\n"
          "      <Value>\n"
          "        <Name>7</Name>\n"
          "        <ValueRepresentation>MaxInactivityTimeDeviceLock</ValueRepresentation>\n"
          "      </Value>\n"
          "      <Value>\n"
          "        <Name>8</Name>\n"
          "        <ValueRepresentation>RequireDeviceEncryption</ValueRepresentation>\n"
          "      </Value>\n"
          "      <Key>\n"
          "        <Category>PolicySource</Category>\n"
          "        <Path>*</Path>\n"
          "        <Representation>Source</Representation>\n"
          "      </Key>\n"
          "    </Key>\n"
          "  </DataSource>\n"
          "</DiagData>";
    if ( !IsStateSeparationEnabled )
      v8 = (const wchar_t *)L"<?xml version=\"1.0\" encoding=\"utf-16\"?>\n"
                             "<DiagData>\n"
                             "  <DataSource name=\"EAS\">\n"
                             "    <Key>\n"
                             "      <Category>EASPolicies</Category>\n"
                             "      <Path>HKLM\\System\\CurrentControlSet\\Control\\Eas\\*</Path>\n"
                             "      <Representation>Type</Representation>\n"
                             "      <Value>\n"
                             "        <Name>1</Name>\n"
                             "        <ValueRepresentation>MinDevicePasswordComplexCharacters</ValueRepresentation>\n"
                             "      </Value>\n"
                             "      <Value>\n"
                             "        <Name>2</Name>\n"
                             "        <ValueRepresentation>MinDevicePasswordLength</ValueRepresentation>\n"
                             "      </Value>\n"
                             "      <Value>\n"
                             "        <Name>3</Name>\n"
                             "        <ValueRepresentation>DevicePasswordExpiration</ValueRepresentation>\n"
                             "      </Value>\n"
                             "      <Value>\n"
                             "        <Name>4</Name>\n"
                             "        <ValueRepresentation>DevicePasswordHistory</ValueRepresentation>\n"
                             "      </Value>\n"
                             "      <Value>\n"
                             "        <Name>5</Name>\n"
                             "        <ValueRepresentation>AllowSimpleDevicePassword</ValueRepresentation>\n"
                             "      </Value>\n"
                             "      <Value>\n"
                             "        <Name>6</Name>\n"
                             "        <ValueRepresentation>MaxDevicePasswordFailedAttempts</ValueRepresentation>\n"
                             "      </Value>\n"
                             "      <Value>\n"
                             "        <Name>7</Name>\n"
                             "        <ValueRepresentation>MaxInactivityTimeDeviceLock</ValueRepresentation>\n"
                             "      </Value>\n"
                             "      <Value>\n"
                             "        <Name>8</Name>\n"
                             "        <ValueRepresentation>RequireDeviceEncryption</ValueRepresentation>\n"
                             "      </Value>\n"
                             "      <Key>\n"
                             "        <Category>PolicySource</Category>\n"
                             "        <Path>*</Path>\n"
                             "        <Representation>Source</Representation>\n"
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
              "  <DataSource name=\"EAS\">\n"
              "    <Key>\n"
              "      <Category>EASPolicies</Category>\n"
              "      <Path>HKLM\\System\\CurrentControlSet\\Control\\Eas\\*</Path>\n"
              "      <Representation>Type</Representation>\n"
              "      <Value>\n"
              "        <Name>1</Name>\n"
              "        <ValueRepresentation>MinDevicePasswordComplexCharacters</ValueRepresentation>\n"
              "      </Value>\n"
              "      <Value>\n"
              "        <Name>2</Name>\n"
              "        <ValueRepresentation>MinDevicePasswordLength</ValueRepresentation>\n"
              "      </Value>\n"
              "      <Value>\n"
              "        <Name>3</Name>\n"
              "        <ValueRepresentation>DevicePasswordExpiration</ValueRepresentation>\n"
              "      </Value>\n"
              "      <Value>\n"
              "        <Name>4</Name>\n"
              "        <ValueRepresentation>DevicePasswordHistory</ValueRepresentation>\n"
              "      </Value>\n"
              "      <Value>\n"
              "        <Name>5</Name>\n"
              "        <ValueRepresentation>AllowSimpleDevicePassword</ValueRepresentation>\n"
              "      </Value>\n"
              "      <Value>\n"
              "        <Name>6</Name>\n"
              "        <ValueRepresentation>MaxDevicePasswordFailedAttempts</ValueRepresentation>\n"
              "      </Value>\n"
              "      <Value>\n"
              "        <Name>7</Name>\n"
              "        <ValueRepresentation>MaxInactivityTimeDeviceLock</ValueRepresentation>\n"
              "      </Value>\n"
              "      <Value>\n"
              "        <Name>8</Name>\n"
              "        <ValueRepresentation>RequireDeviceEncryption</ValueRepresentation>\n"
              "      </Value>\n"
              "      <Key>\n"
              "        <Category>PolicySource</Category>\n"
              "        <Path>*</Path>\n"
              "        <Representation>Source</Representation>\n"
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
    (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmdiagnostics\\dll\\easpolicydiagdata.cpp",
    (const char *)(unsigned int)StreamOnHGlobal,
    v12);
LABEL_15:
  Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&v14);
  return v4;
}

```

## disassembly

```asm
0x180105980  mov     rax, rsp
0x180105983  mov     [rax+8], rbx
0x180105987  mov     [rax+10h], rbp
0x18010598b  push    rsi
0x18010598c  push    rdi
0x18010598d  push    r14; int
0x18010598f  sub     rsp, 20h
0x180105993  mov     rsi, rdx
0x180105996  xor     ebp, ebp
0x180105998  mov     [rax+18h], rbp
0x18010599c  mov     [rax+20h], rbp
0x1801059a0  mov     r8, rdx; ppstm
0x1801059a3  lea     edx, [rbp+1]; fDeleteOnRelease
0x1801059a6  xor     ecx, ecx; hGlobal
0x1801059a8  call    cs:__imp_CreateStreamOnHGlobal
0x1801059af  nop     dword ptr [rax+rax+00h]
0x1801059b4  mov     ebx, eax
0x1801059b6  test    eax, eax
0x1801059b8  jns     short loc_1801059BF
0x1801059ba  lea     edx, [rbp+31h]
0x1801059bd  jmp     short loc_180105A07
0x1801059bf  call    cs:__imp_RtlIsStateSeparationEnabled
0x1801059c6  nop     dword ptr [rax+rax+00h]
0x1801059cb  lea     r14, aXmlVersion10En_27; "<?xml version=\"1.0\" encoding=\"utf-16"...
0x1801059d2  lea     rdi, aXmlVersion10En_3; "<?xml version=\"1.0\" encoding=\"utf-16"...
0x1801059d9  mov     rdx, rdi
0x1801059dc  test    al, al
0x1801059de  cmovz   rdx, r14; unsigned __int64
0x1801059e2  or      rcx, 0FFFFFFFFFFFFFFFFh
0x1801059e6  inc     rcx
0x1801059e9  cmp     [rdx+rcx*2], bp
0x1801059ed  jnz     short loc_1801059E6
0x1801059ef  inc     rcx; unsigned __int64
0x1801059f2  lea     r8, [rsp+38h+cbInit]; unsigned __int64 *
0x1801059f7  call    ?ULongLongMult@@YAJ_K0PEA_K@Z; ULongLongMult(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x1801059fc  mov     ebx, eax
0x1801059fe  test    eax, eax
0x180105a00  jns     short loc_180105A1D
0x180105a02  mov     edx, 32h ; '2'; void *
0x180105a07  mov     rcx, [rsp+38h]; this
0x180105a0c  mov     r9d, eax; char *
0x180105a0f  lea     r8, aOnecoreuapAdmi_1; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x180105a16  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180105a1b  jmp     short loc_180105A6B
0x180105a1d  call    cs:__imp_RtlIsStateSeparationEnabled
0x180105a24  nop     dword ptr [rax+rax+00h]
0x180105a29  test    al, al
0x180105a2b  cmovz   rdi, r14
0x180105a2f  mov     edx, dword ptr [rsp+38h+cbInit]; cbInit
0x180105a33  mov     rcx, rdi; pInit
0x180105a36  call    cs:__imp_SHCreateMemStream
0x180105a3d  nop     dword ptr [rax+rax+00h]
0x180105a42  mov     rdx, rax
0x180105a45  lea     rcx, [rsp+38h+arg_10]
0x180105a4a  call    ??4?$ComPtr@UIStream@@@WRL@Microsoft@@QEAAAEAV012@PEAUIStream@@@Z; Microsoft::WRL::ComPtr<IStream>::operator=(IStream *)
0x180105a4f  mov     rdx, [rsi]; struct IStream *
0x180105a52  mov     rcx, [rsp+38h+arg_10]; struct IStream *
0x180105a57  call    ?CreateDiagnosticData@@YAJPEAUIStream@@0@Z; CreateDiagnosticData(IStream *,IStream *)
0x180105a5c  mov     ebx, eax
0x180105a5e  test    eax, eax
0x180105a60  jns     short loc_180105A69
0x180105a62  mov     edx, 37h ; '7'
0x180105a67  jmp     short loc_180105A07
0x180105a69  mov     ebx, ebp
0x180105a6b  lea     rcx, [rsp+38h+arg_10]
0x180105a70  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x180105a75  mov     eax, ebx
0x180105a77  mov     rbx, [rsp+38h+arg_0]
0x180105a7c  mov     rbp, [rsp+38h+arg_8]
0x180105a81  add     rsp, 20h
0x180105a85  pop     r14
0x180105a87  pop     rdi
0x180105a88  pop     rsi
0x180105a89  retn
```
