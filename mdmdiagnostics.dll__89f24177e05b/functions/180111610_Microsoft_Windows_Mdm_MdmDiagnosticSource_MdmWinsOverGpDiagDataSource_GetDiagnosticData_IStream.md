# Microsoft::Windows::Mdm::MdmDiagnosticSource::MdmWinsOverGpDiagDataSource::GetDiagnosticData(IStream * *)

- ea: `0x180111610`
- end: `0x180111702`
- name: `?GetDiagnosticData@MdmWinsOverGpDiagDataSource@MdmDiagnosticSource@Mdm@Windows@Microsoft@@UEAAJPEAPEAUIStream@@@Z`
- size: `242`
- prototype: `int(Microsoft::Windows::Mdm::MdmDiagnosticSource::MdmWinsOverGpDiagDataSource *__hidden this, struct IStream **)`
- caller_count: `0`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callees

- `0x1800ead14`
- `0x1800ece5c`
- `0x1800f7f10`
- `0x1800f8680`
- `0x180111610`
- `0x180122018`

## import_xrefs

- `ntdll!RtlIsStateSeparationEnabled` at `0x180111649`
- `ntdll!RtlIsStateSeparationEnabled` at `0x1801116a1`
- `ntdll!RtlIsStateSeparationEnabled` at `0x180111649`
- `ntdll!RtlIsStateSeparationEnabled` at `0x1801116a1`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x180111638`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x180111638`
- `api-ms-win-shcore-stream-l1-1-0!SHCreateMemStream` at `0x1801116b4`
- `api-ms-win-shcore-stream-l1-1-0!SHCreateMemStream` at `0x1801116b4`

## string_xrefs

- `0x180111656`: `<?xml version="1.0" encoding="utf-16"?>\n        <DiagData>\n          <DataSource name="OSDataMdmWinsOverGp">\n            <key>\n              <Category>BlockingRecords</Category>\n              <Path>HKLM\OSData\Software\Microsoft\MdmWins</Path>\n              <key>\n                <Category>Target</Category>\n                <Path>*</Path>\n                <Representation>UserSid</Representation>\n                <key>\n                  <Category>NameSpace</Category>\n                  <Pa`
- `0x18011164f`: `<?xml version="1.0" encoding="utf-16"?>\n        <DiagData>\n          <DataSource name="MdmWinsOverGp">\n            <key>\n              <Category>BlockingRecords</Category>\n              <Path>HKLM\Software\Microsoft\MdmWins</Path>\n              <key>\n                <Category>Target</Category>\n                <Path>*</Path>\n                <Representation>UserSid</Representation>\n                <key>\n                  <Category>NameSpace</Category>\n                  <Path>*</Path>\n`
- `0x180111693`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\dll\mdmwinsovergpdiagdata.cpp`

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
0x180111610  mov     rax, rsp
0x180111613  mov     [rax+8], rbx
0x180111617  mov     [rax+10h], rbp
0x18011161b  push    rsi
0x18011161c  push    rdi
0x18011161d  push    r14; int
0x18011161f  sub     rsp, 20h
0x180111623  mov     rsi, rdx
0x180111626  xor     ebp, ebp
0x180111628  mov     [rax+18h], rbp
0x18011162c  mov     [rax+20h], rbp
0x180111630  mov     r8, rdx; ppstm
0x180111633  lea     edx, [rbp+1]; fDeleteOnRelease
0x180111636  xor     ecx, ecx; hGlobal
0x180111638  call    cs:__imp_CreateStreamOnHGlobal
0x18011163e  mov     ebx, eax
0x180111640  test    eax, eax
0x180111642  jns     short loc_180111649
0x180111644  lea     edx, [rbp+22h]
0x180111647  jmp     short loc_18011168B
0x180111649  call    cs:__imp_RtlIsStateSeparationEnabled
0x18011164f  lea     r14, aXmlVersion10En_9; "<?xml version=\"1.0\" encoding=\"utf-16"...
0x180111656  lea     rdi, aXmlVersion10En_11; "<?xml version=\"1.0\" encoding=\"utf-16"...
0x18011165d  mov     rdx, rdi
0x180111660  test    al, al
0x180111662  cmovz   rdx, r14; unsigned __int64
0x180111666  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18011166a  inc     rcx
0x18011166d  cmp     [rdx+rcx*2], bp
0x180111671  jnz     short loc_18011166A
0x180111673  inc     rcx; unsigned __int64
0x180111676  lea     r8, [rsp+38h+cbInit]; unsigned __int64 *
0x18011167b  call    ?ULongLongMult@@YAJ_K0PEA_K@Z; ULongLongMult(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x180111680  mov     ebx, eax
0x180111682  test    eax, eax
0x180111684  jns     short loc_1801116A1
0x180111686  mov     edx, 23h ; '#'; void *
0x18011168b  mov     rcx, [rsp+38h]; this
0x180111690  mov     r9d, eax; char *
0x180111693  lea     r8, aOnecoreuapAdmi_25; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x18011169a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18011169f  jmp     short loc_1801116E3
0x1801116a1  call    cs:__imp_RtlIsStateSeparationEnabled
0x1801116a7  test    al, al
0x1801116a9  cmovz   rdi, r14
0x1801116ad  mov     edx, dword ptr [rsp+38h+cbInit]; cbInit
0x1801116b1  mov     rcx, rdi; pInit
0x1801116b4  call    cs:__imp_SHCreateMemStream
0x1801116ba  mov     rdx, rax
0x1801116bd  lea     rcx, [rsp+38h+arg_10]
0x1801116c2  call    ??4?$ComPtr@UIStream@@@WRL@Microsoft@@QEAAAEAV012@PEAUIStream@@@Z; Microsoft::WRL::ComPtr<IStream>::operator=(IStream *)
0x1801116c7  mov     rdx, [rsi]; struct IStream *
0x1801116ca  mov     rcx, [rsp+38h+arg_10]; struct IStream *
0x1801116cf  call    ?CreateDiagnosticData@@YAJPEAUIStream@@0@Z; CreateDiagnosticData(IStream *,IStream *)
0x1801116d4  mov     ebx, eax
0x1801116d6  test    eax, eax
0x1801116d8  jns     short loc_1801116E1
0x1801116da  mov     edx, 27h ; '''
0x1801116df  jmp     short loc_18011168B
0x1801116e1  mov     ebx, ebp
0x1801116e3  lea     rcx, [rsp+38h+arg_10]
0x1801116e8  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x1801116ed  mov     eax, ebx
0x1801116ef  mov     rbx, [rsp+38h+arg_0]
0x1801116f4  mov     rbp, [rsp+38h+arg_8]
0x1801116f9  add     rsp, 20h
0x1801116fd  pop     r14
0x1801116ff  pop     rdi
0x180111700  pop     rsi
0x180111701  retn
```
