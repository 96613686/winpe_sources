# Microsoft::Windows::Mdm::MdmDiagnosticSource::EASPolicyDiagDataSource::GetDiagnosticData(IStream * *)

- ea: `0x180104730`
- end: `0x180104822`
- name: `?GetDiagnosticData@EASPolicyDiagDataSource@MdmDiagnosticSource@Mdm@Windows@Microsoft@@UEAAJPEAPEAUIStream@@@Z`
- size: `242`
- prototype: `int(Microsoft::Windows::Mdm::MdmDiagnosticSource::EASPolicyDiagDataSource *__hidden this, struct IStream **)`
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x1800ead14`
- `0x1800ece5c`
- `0x1800f7f10`
- `0x1800f8680`
- `0x180104730`
- `0x180122018`

## import_xrefs

- `ntdll!RtlIsStateSeparationEnabled` at `0x180104769`
- `ntdll!RtlIsStateSeparationEnabled` at `0x1801047c1`
- `ntdll!RtlIsStateSeparationEnabled` at `0x180104769`
- `ntdll!RtlIsStateSeparationEnabled` at `0x1801047c1`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x180104758`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x180104758`
- `api-ms-win-shcore-stream-l1-1-0!SHCreateMemStream` at `0x1801047d4`
- `api-ms-win-shcore-stream-l1-1-0!SHCreateMemStream` at `0x1801047d4`

## string_xrefs

- `0x18010476f`: `<?xml version="1.0" encoding="utf-16"?>\n<DiagData>\n  <DataSource name="EAS">\n    <Key>\n      <Category>EASPolicies</Category>\n      <Path>HKLM\System\CurrentControlSet\Control\Eas\*</Path>\n      <Representation>Type</Representation>\n      <Value>\n        <Name>1</Name>\n        <ValueRepresentation>MinDevicePasswordComplexCharacters</ValueRepresentation>\n      </Value>\n      <Value>\n        <Name>2</Name>\n        <ValueRepresentation>MinDevicePasswordLength</ValueRepresentation>\n   `
- `0x180104776`: `<?xml version="1.0" encoding="utf-16"?>\n<DiagData>\n  <DataSource name="OSDataEAS">\n    <Key>\n      <Category>EASPolicies</Category>\n      <Path>HKLM\OSData\System\CurrentControlSet\Control\Eas\*</Path>\n      <Representation>Type</Representation>\n      <Value>\n        <Name>1</Name>\n        <ValueRepresentation>MinDevicePasswordComplexCharacters</ValueRepresentation>\n      </Value>\n      <Value>\n        <Name>2</Name>\n        <ValueRepresentation>MinDevicePasswordLength</ValueReprese`
- `0x1801047b3`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\dll\easpolicydiagdata.cpp`

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
0x180104730  mov     rax, rsp
0x180104733  mov     [rax+8], rbx
0x180104737  mov     [rax+10h], rbp
0x18010473b  push    rsi
0x18010473c  push    rdi
0x18010473d  push    r14; int
0x18010473f  sub     rsp, 20h
0x180104743  mov     rsi, rdx
0x180104746  xor     ebp, ebp
0x180104748  mov     [rax+18h], rbp
0x18010474c  mov     [rax+20h], rbp
0x180104750  mov     r8, rdx; ppstm
0x180104753  lea     edx, [rbp+1]; fDeleteOnRelease
0x180104756  xor     ecx, ecx; hGlobal
0x180104758  call    cs:__imp_CreateStreamOnHGlobal
0x18010475e  mov     ebx, eax
0x180104760  test    eax, eax
0x180104762  jns     short loc_180104769
0x180104764  lea     edx, [rbp+31h]
0x180104767  jmp     short loc_1801047AB
0x180104769  call    cs:__imp_RtlIsStateSeparationEnabled
0x18010476f  lea     r14, aXmlVersion10En_27; "<?xml version=\"1.0\" encoding=\"utf-16"...
0x180104776  lea     rdi, aXmlVersion10En_3; "<?xml version=\"1.0\" encoding=\"utf-16"...
0x18010477d  mov     rdx, rdi
0x180104780  test    al, al
0x180104782  cmovz   rdx, r14; unsigned __int64
0x180104786  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18010478a  inc     rcx
0x18010478d  cmp     [rdx+rcx*2], bp
0x180104791  jnz     short loc_18010478A
0x180104793  inc     rcx; unsigned __int64
0x180104796  lea     r8, [rsp+38h+cbInit]; unsigned __int64 *
0x18010479b  call    ?ULongLongMult@@YAJ_K0PEA_K@Z; ULongLongMult(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x1801047a0  mov     ebx, eax
0x1801047a2  test    eax, eax
0x1801047a4  jns     short loc_1801047C1
0x1801047a6  mov     edx, 32h ; '2'; void *
0x1801047ab  mov     rcx, [rsp+38h]; this
0x1801047b0  mov     r9d, eax; char *
0x1801047b3  lea     r8, aOnecoreuapAdmi_1; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x1801047ba  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801047bf  jmp     short loc_180104803
0x1801047c1  call    cs:__imp_RtlIsStateSeparationEnabled
0x1801047c7  test    al, al
0x1801047c9  cmovz   rdi, r14
0x1801047cd  mov     edx, dword ptr [rsp+38h+cbInit]; cbInit
0x1801047d1  mov     rcx, rdi; pInit
0x1801047d4  call    cs:__imp_SHCreateMemStream
0x1801047da  mov     rdx, rax
0x1801047dd  lea     rcx, [rsp+38h+arg_10]
0x1801047e2  call    ??4?$ComPtr@UIStream@@@WRL@Microsoft@@QEAAAEAV012@PEAUIStream@@@Z; Microsoft::WRL::ComPtr<IStream>::operator=(IStream *)
0x1801047e7  mov     rdx, [rsi]; struct IStream *
0x1801047ea  mov     rcx, [rsp+38h+arg_10]; struct IStream *
0x1801047ef  call    ?CreateDiagnosticData@@YAJPEAUIStream@@0@Z; CreateDiagnosticData(IStream *,IStream *)
0x1801047f4  mov     ebx, eax
0x1801047f6  test    eax, eax
0x1801047f8  jns     short loc_180104801
0x1801047fa  mov     edx, 37h ; '7'
0x1801047ff  jmp     short loc_1801047AB
0x180104801  mov     ebx, ebp
0x180104803  lea     rcx, [rsp+38h+arg_10]
0x180104808  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x18010480d  mov     eax, ebx
0x18010480f  mov     rbx, [rsp+38h+arg_0]
0x180104814  mov     rbp, [rsp+38h+arg_8]
0x180104819  add     rsp, 20h
0x18010481d  pop     r14
0x18010481f  pop     rdi
0x180104820  pop     rsi
0x180104821  retn
```
