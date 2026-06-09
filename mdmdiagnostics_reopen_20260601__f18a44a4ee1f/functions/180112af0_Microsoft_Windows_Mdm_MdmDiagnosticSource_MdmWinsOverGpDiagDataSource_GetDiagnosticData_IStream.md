# Microsoft::Windows::Mdm::MdmDiagnosticSource::MdmWinsOverGpDiagDataSource::GetDiagnosticData(IStream * *)

- ea: `0x180112af0`
- end: `0x180112bfb`
- name: `?GetDiagnosticData@MdmWinsOverGpDiagDataSource@MdmDiagnosticSource@Mdm@Windows@Microsoft@@UEAAJPEAPEAUIStream@@@Z`
- size: `267`
- prototype: `int(Microsoft::Windows::Mdm::MdmDiagnosticSource::MdmWinsOverGpDiagDataSource *__hidden this, struct IStream **)`
- caller_count: `0`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callees

- `0x1800eb1ac`
- `0x1800ed46c`
- `0x1800f8e70`
- `0x1800f962c`
- `0x180112af0`
- `0x180123aa8`

## import_xrefs

- `ntdll!RtlIsStateSeparationEnabled` at `0x180112b2f`
- `ntdll!RtlIsStateSeparationEnabled` at `0x180112b8d`
- `ntdll!RtlIsStateSeparationEnabled` at `0x180112b2f`
- `ntdll!RtlIsStateSeparationEnabled` at `0x180112b8d`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x180112b18`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x180112b18`
- `api-ms-win-shcore-stream-l1-1-0!SHCreateMemStream` at `0x180112ba6`
- `api-ms-win-shcore-stream-l1-1-0!SHCreateMemStream` at `0x180112ba6`

## string_xrefs

- `0x180112b3b`: `<?xml version="1.0" encoding="utf-16"?>\n        <DiagData>\n          <DataSource name="MdmWinsOverGp">\n            <key>\n              <Category>BlockingRecords</Category>\n              <Path>HKLM\Software\Microsoft\MdmWins</Path>\n              <key>\n                <Category>Target</Category>\n                <Path>*</Path>\n                <Representation>UserSid</Representation>\n                <key>\n                  <Category>NameSpace</Category>\n                  <Path>*</Path>\n`
- `0x180112b42`: `<?xml version="1.0" encoding="utf-16"?>\n        <DiagData>\n          <DataSource name="OSDataMdmWinsOverGp">\n            <key>\n              <Category>BlockingRecords</Category>\n              <Path>HKLM\OSData\Software\Microsoft\MdmWins</Path>\n              <key>\n                <Category>Target</Category>\n                <Path>*</Path>\n                <Representation>UserSid</Representation>\n                <key>\n                  <Category>NameSpace</Category>\n                  <Pa`
- `0x180112b7f`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\dll\mdmwinsovergpdiagdata.cpp`

## pseudocode

```c
__int64 __fastcall Microsoft::Windows::Mdm::MdmDiagnosticSource::MdmWinsOverGpDiagDataSource::GetDiagnosticData(
        Microsoft::Windows::Mdm::MdmDiagnosticSource::MdmWinsOverGpDiagDataSource *this,
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
                        "          <DataSource name=\"OSDataMdmWinsOverGp\">\n"
                        "            <key>\n"
                        "              <Category>BlockingRecords</Category>\n"
                        "              <Path>HKLM\\OSData\\Software\\Microsoft\\MdmWins</Path>\n"
                        "              <key>\n"
                        "                <Category>Target</Category>\n"
                        "                <Path>*</Path>\n"
                        "                <Representation>UserSid</Representation>\n"
                        "                <key>\n"
                        "                  <Category>NameSpace</Category>\n"
                        "                  <Path>*</Path>\n"
                        "                  <Representation>BlockedNamespace</Representation>\n"
                        "                  <key>\n"
                        "                    <Category>Value</Category>\n"
                        "                    <Path>*</Path>\n"
                        "                    <Representation>BlockedValue</Representation>\n"
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
          "          <DataSource name=\"OSDataMdmWinsOverGp\">\n"
          "            <key>\n"
          "              <Category>BlockingRecords</Category>\n"
          "              <Path>HKLM\\OSData\\Software\\Microsoft\\MdmWins</Path>\n"
          "              <key>\n"
          "                <Category>Target</Category>\n"
          "                <Path>*</Path>\n"
          "                <Representation>UserSid</Representation>\n"
          "                <key>\n"
          "                  <Category>NameSpace</Category>\n"
          "                  <Path>*</Path>\n"
          "                  <Representation>BlockedNamespace</Representation>\n"
          "                  <key>\n"
          "                    <Category>Value</Category>\n"
          "                    <Path>*</Path>\n"
          "                    <Representation>BlockedValue</Representation>\n"
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
                             "          <DataSource name=\"MdmWinsOverGp\">\n"
                             "            <key>\n"
                             "              <Category>BlockingRecords</Category>\n"
                             "              <Path>HKLM\\Software\\Microsoft\\MdmWins</Path>\n"
                             "              <key>\n"
                             "                <Category>Target</Category>\n"
                             "                <Path>*</Path>\n"
                             "                <Representation>UserSid</Representation>\n"
                             "                <key>\n"
                             "                  <Category>NameSpace</Category>\n"
                             "                  <Path>*</Path>\n"
                             "                  <Representation>BlockedNamespace</Representation>\n"
                             "                  <key>\n"
                             "                    <Category>Value</Category>\n"
                             "                    <Path>*</Path>\n"
                             "                    <Representation>BlockedValue</Representation>\n"
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
              "          <DataSource name=\"MdmWinsOverGp\">\n"
              "            <key>\n"
              "              <Category>BlockingRecords</Category>\n"
              "              <Path>HKLM\\Software\\Microsoft\\MdmWins</Path>\n"
              "              <key>\n"
              "                <Category>Target</Category>\n"
              "                <Path>*</Path>\n"
              "                <Representation>UserSid</Representation>\n"
              "                <key>\n"
              "                  <Category>NameSpace</Category>\n"
              "                  <Path>*</Path>\n"
              "                  <Representation>BlockedNamespace</Representation>\n"
              "                  <key>\n"
              "                    <Category>Value</Category>\n"
              "                    <Path>*</Path>\n"
              "                    <Representation>BlockedValue</Representation>\n"
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
      v5 = 39;
    }
    else
    {
      v5 = 35;
    }
  }
  else
  {
    v5 = 34;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v5,
    (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmdiagnostics\\dll\\mdmwinsovergpdiagdata.cpp",
    (const char *)(unsigned int)StreamOnHGlobal,
    v12);
LABEL_15:
  Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&v14);
  return v4;
}

```

## disassembly

```asm
0x180112af0  mov     rax, rsp
0x180112af3  mov     [rax+8], rbx
0x180112af7  mov     [rax+10h], rbp
0x180112afb  push    rsi
0x180112afc  push    rdi
0x180112afd  push    r14; int
0x180112aff  sub     rsp, 20h
0x180112b03  mov     rsi, rdx
0x180112b06  xor     ebp, ebp
0x180112b08  mov     [rax+18h], rbp
0x180112b0c  mov     [rax+20h], rbp
0x180112b10  mov     r8, rdx; ppstm
0x180112b13  lea     edx, [rbp+1]; fDeleteOnRelease
0x180112b16  xor     ecx, ecx; hGlobal
0x180112b18  call    cs:__imp_CreateStreamOnHGlobal
0x180112b1f  nop     dword ptr [rax+rax+00h]
0x180112b24  mov     ebx, eax
0x180112b26  test    eax, eax
0x180112b28  jns     short loc_180112B2F
0x180112b2a  lea     edx, [rbp+22h]
0x180112b2d  jmp     short loc_180112B77
0x180112b2f  call    cs:__imp_RtlIsStateSeparationEnabled
0x180112b36  nop     dword ptr [rax+rax+00h]
0x180112b3b  lea     r14, aXmlVersion10En_9; "<?xml version=\"1.0\" encoding=\"utf-16"...
0x180112b42  lea     rdi, aXmlVersion10En_11; "<?xml version=\"1.0\" encoding=\"utf-16"...
0x180112b49  mov     rdx, rdi
0x180112b4c  test    al, al
0x180112b4e  cmovz   rdx, r14; unsigned __int64
0x180112b52  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180112b56  inc     rcx
0x180112b59  cmp     [rdx+rcx*2], bp
0x180112b5d  jnz     short loc_180112B56
0x180112b5f  inc     rcx; unsigned __int64
0x180112b62  lea     r8, [rsp+38h+cbInit]; unsigned __int64 *
0x180112b67  call    ?ULongLongMult@@YAJ_K0PEA_K@Z; ULongLongMult(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x180112b6c  mov     ebx, eax
0x180112b6e  test    eax, eax
0x180112b70  jns     short loc_180112B8D
0x180112b72  mov     edx, 23h ; '#'; void *
0x180112b77  mov     rcx, [rsp+38h]; this
0x180112b7c  mov     r9d, eax; char *
0x180112b7f  lea     r8, aOnecoreuapAdmi_25; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x180112b86  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180112b8b  jmp     short loc_180112BDB
0x180112b8d  call    cs:__imp_RtlIsStateSeparationEnabled
0x180112b94  nop     dword ptr [rax+rax+00h]
0x180112b99  test    al, al
0x180112b9b  cmovz   rdi, r14
0x180112b9f  mov     edx, dword ptr [rsp+38h+cbInit]; cbInit
0x180112ba3  mov     rcx, rdi; pInit
0x180112ba6  call    cs:__imp_SHCreateMemStream
0x180112bad  nop     dword ptr [rax+rax+00h]
0x180112bb2  mov     rdx, rax
0x180112bb5  lea     rcx, [rsp+38h+arg_10]
0x180112bba  call    ??4?$ComPtr@UIStream@@@WRL@Microsoft@@QEAAAEAV012@PEAUIStream@@@Z; Microsoft::WRL::ComPtr<IStream>::operator=(IStream *)
0x180112bbf  mov     rdx, [rsi]; struct IStream *
0x180112bc2  mov     rcx, [rsp+38h+arg_10]; struct IStream *
0x180112bc7  call    ?CreateDiagnosticData@@YAJPEAUIStream@@0@Z; CreateDiagnosticData(IStream *,IStream *)
0x180112bcc  mov     ebx, eax
0x180112bce  test    eax, eax
0x180112bd0  jns     short loc_180112BD9
0x180112bd2  mov     edx, 27h ; '''
0x180112bd7  jmp     short loc_180112B77
0x180112bd9  mov     ebx, ebp
0x180112bdb  lea     rcx, [rsp+38h+arg_10]
0x180112be0  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x180112be5  mov     eax, ebx
0x180112be7  mov     rbx, [rsp+38h+arg_0]
0x180112bec  mov     rbp, [rsp+38h+arg_8]
0x180112bf1  add     rsp, 20h
0x180112bf5  pop     r14
0x180112bf7  pop     rdi
0x180112bf8  pop     rsi
0x180112bf9  retn
```
