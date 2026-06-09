# Microsoft::Windows::Mdm::MdmDiagnosticSource::AutoDiagnosticsDataSource::GetDiagnosticData(IStream * *)

- ea: `0x1800f88e0`
- end: `0x1800f89d2`
- name: `?GetDiagnosticData@AutoDiagnosticsDataSource@MdmDiagnosticSource@Mdm@Windows@Microsoft@@UEAAJPEAPEAUIStream@@@Z`
- size: `242`
- prototype: `int(Microsoft::Windows::Mdm::MdmDiagnosticSource::AutoDiagnosticsDataSource *__hidden this, struct IStream **)`
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x1800ead14`
- `0x1800ece5c`
- `0x1800f7f10`
- `0x1800f8680`
- `0x1800f88e0`
- `0x180122018`

## import_xrefs

- `ntdll!RtlIsStateSeparationEnabled` at `0x1800f8919`
- `ntdll!RtlIsStateSeparationEnabled` at `0x1800f8971`
- `ntdll!RtlIsStateSeparationEnabled` at `0x1800f8919`
- `ntdll!RtlIsStateSeparationEnabled` at `0x1800f8971`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x1800f8908`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x1800f8908`
- `api-ms-win-shcore-stream-l1-1-0!SHCreateMemStream` at `0x1800f8984`
- `api-ms-win-shcore-stream-l1-1-0!SHCreateMemStream` at `0x1800f8984`

## string_xrefs

- `0x1800f891f`: `<?xml version="1.0" encoding="utf-16"?>\n<DiagData>\n  <DataSource name="Diagnostics">\n    <Key>\n      <Category>ErrorLog</Category>\n      <Path>HKLM\Software\Microsoft\Provisioning\Diagnostics\*</Path>\n      <Representation>Component</Representation>   \n      <Value>\n         <Name>*</Name>\n         <ValueRepresentation>*</ValueRepresentation>\n      </Value>\n      <Key>\n         <Category>SubComponent</Category>\n         <Path>*</Path>\n         <Representation>Name</Representation>\`
- `0x1800f8926`: `<?xml version="1.0" encoding="utf-16"?>\n<DiagData>\n  <DataSource name="OSDataDiagnostics">\n    <Key>\n      <Category>ErrorLog</Category>\n      <Path>HKLM\OSData\Software\Microsoft\Provisioning\Diagnostics\*</Path>\n      <Representation>Component</Representation>   \n      <Value>\n         <Name>*</Name>\n         <ValueRepresentation>*</ValueRepresentation>\n      </Value>\n      <Key>\n         <Category>SubComponent</Category>\n         <Path>*</Path>\n         <Representation>Name</Rep`
- `0x1800f8963`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\dll\diagnosticsdata.cpp`

## pseudocode

```c
__int64 __fastcall Microsoft::Windows::Mdm::MdmDiagnosticSource::AutoDiagnosticsDataSource::GetDiagnosticData(
        Microsoft::Windows::Mdm::MdmDiagnosticSource::AutoDiagnosticsDataSource *this,
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
                        "  <DataSource name=\"OSDataDiagnostics\">\n"
                        "    <Key>\n"
                        "      <Category>ErrorLog</Category>\n"
                        "      <Path>HKLM\\OSData\\Software\\Microsoft\\Provisioning\\Diagnostics\\*</Path>\n"
                        "      <Representation>Component</Representation>   \n"
                        "      <Value>\n"
                        "         <Name>*</Name>\n"
                        "         <ValueRepresentation>*</ValueRepresentation>\n"
                        "      </Value>\n"
                        "      <Key>\n"
                        "         <Category>SubComponent</Category>\n"
                        "         <Path>*</Path>\n"
                        "         <Representation>Name</Representation>\n"
                        "         <Value>\n"
                        "           <Name>*</Name>\n"
                        "           <ValueRepresentation>*</ValueRepresentation>\n"
                        "         </Value>\n"
                        "      </Key>\n"
                        "    </Key>\n"
                        "  </DataSource>\n"
                        "</DiagData>";
    v8 = L"<?xml version=\"1.0\" encoding=\"utf-16\"?>\n"
          "<DiagData>\n"
          "  <DataSource name=\"OSDataDiagnostics\">\n"
          "    <Key>\n"
          "      <Category>ErrorLog</Category>\n"
          "      <Path>HKLM\\OSData\\Software\\Microsoft\\Provisioning\\Diagnostics\\*</Path>\n"
          "      <Representation>Component</Representation>   \n"
          "      <Value>\n"
          "         <Name>*</Name>\n"
          "         <ValueRepresentation>*</ValueRepresentation>\n"
          "      </Value>\n"
          "      <Key>\n"
          "         <Category>SubComponent</Category>\n"
          "         <Path>*</Path>\n"
          "         <Representation>Name</Representation>\n"
          "         <Value>\n"
          "           <Name>*</Name>\n"
          "           <ValueRepresentation>*</ValueRepresentation>\n"
          "         </Value>\n"
          "      </Key>\n"
          "    </Key>\n"
          "  </DataSource>\n"
          "</DiagData>";
    if ( !IsStateSeparationEnabled )
      v8 = (const wchar_t *)L"<?xml version=\"1.0\" encoding=\"utf-16\"?>\n"
                             "<DiagData>\n"
                             "  <DataSource name=\"Diagnostics\">\n"
                             "    <Key>\n"
                             "      <Category>ErrorLog</Category>\n"
                             "      <Path>HKLM\\Software\\Microsoft\\Provisioning\\Diagnostics\\*</Path>\n"
                             "      <Representation>Component</Representation>   \n"
                             "      <Value>\n"
                             "         <Name>*</Name>\n"
                             "         <ValueRepresentation>*</ValueRepresentation>\n"
                             "      </Value>\n"
                             "      <Key>\n"
                             "         <Category>SubComponent</Category>\n"
                             "         <Path>*</Path>\n"
                             "         <Representation>Name</Representation>\n"
                             "         <Value>\n"
                             "           <Name>*</Name>\n"
                             "           <ValueRepresentation>*</ValueRepresentation>\n"
                             "         </Value>\n"
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
              "  <DataSource name=\"Diagnostics\">\n"
              "    <Key>\n"
              "      <Category>ErrorLog</Category>\n"
              "      <Path>HKLM\\Software\\Microsoft\\Provisioning\\Diagnostics\\*</Path>\n"
              "      <Representation>Component</Representation>   \n"
              "      <Value>\n"
              "         <Name>*</Name>\n"
              "         <ValueRepresentation>*</ValueRepresentation>\n"
              "      </Value>\n"
              "      <Key>\n"
              "         <Category>SubComponent</Category>\n"
              "         <Path>*</Path>\n"
              "         <Representation>Name</Representation>\n"
              "         <Value>\n"
              "           <Name>*</Name>\n"
              "           <ValueRepresentation>*</ValueRepresentation>\n"
              "         </Value>\n"
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
    (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmdiagnostics\\dll\\diagnosticsdata.cpp",
    (const char *)(unsigned int)StreamOnHGlobal,
    v12);
LABEL_15:
  Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&v14);
  return v4;
}

```

## disassembly

```asm
0x1800f88e0  mov     rax, rsp
0x1800f88e3  mov     [rax+8], rbx
0x1800f88e7  mov     [rax+10h], rbp
0x1800f88eb  push    rsi
0x1800f88ec  push    rdi
0x1800f88ed  push    r14; int
0x1800f88ef  sub     rsp, 20h
0x1800f88f3  mov     rsi, rdx
0x1800f88f6  xor     ebp, ebp
0x1800f88f8  mov     [rax+18h], rbp
0x1800f88fc  mov     [rax+20h], rbp
0x1800f8900  mov     r8, rdx; ppstm
0x1800f8903  lea     edx, [rbp+1]; fDeleteOnRelease
0x1800f8906  xor     ecx, ecx; hGlobal
0x1800f8908  call    cs:__imp_CreateStreamOnHGlobal
0x1800f890e  mov     ebx, eax
0x1800f8910  test    eax, eax
0x1800f8912  jns     short loc_1800F8919
0x1800f8914  lea     edx, [rbp+31h]
0x1800f8917  jmp     short loc_1800F895B
0x1800f8919  call    cs:__imp_RtlIsStateSeparationEnabled
0x1800f891f  lea     r14, aXmlVersion10En_14; "<?xml version=\"1.0\" encoding=\"utf-16"...
0x1800f8926  lea     rdi, aXmlVersion10En_24; "<?xml version=\"1.0\" encoding=\"utf-16"...
0x1800f892d  mov     rdx, rdi
0x1800f8930  test    al, al
0x1800f8932  cmovz   rdx, r14; unsigned __int64
0x1800f8936  or      rcx, 0FFFFFFFFFFFFFFFFh
0x1800f893a  inc     rcx
0x1800f893d  cmp     [rdx+rcx*2], bp
0x1800f8941  jnz     short loc_1800F893A
0x1800f8943  inc     rcx; unsigned __int64
0x1800f8946  lea     r8, [rsp+38h+cbInit]; unsigned __int64 *
0x1800f894b  call    ?ULongLongMult@@YAJ_K0PEA_K@Z; ULongLongMult(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x1800f8950  mov     ebx, eax
0x1800f8952  test    eax, eax
0x1800f8954  jns     short loc_1800F8971
0x1800f8956  mov     edx, 32h ; '2'; void *
0x1800f895b  mov     rcx, [rsp+38h]; this
0x1800f8960  mov     r9d, eax; char *
0x1800f8963  lea     r8, aOnecoreuapAdmi_10; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x1800f896a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800f896f  jmp     short loc_1800F89B3
0x1800f8971  call    cs:__imp_RtlIsStateSeparationEnabled
0x1800f8977  test    al, al
0x1800f8979  cmovz   rdi, r14
0x1800f897d  mov     edx, dword ptr [rsp+38h+cbInit]; cbInit
0x1800f8981  mov     rcx, rdi; pInit
0x1800f8984  call    cs:__imp_SHCreateMemStream
0x1800f898a  mov     rdx, rax
0x1800f898d  lea     rcx, [rsp+38h+arg_10]
0x1800f8992  call    ??4?$ComPtr@UIStream@@@WRL@Microsoft@@QEAAAEAV012@PEAUIStream@@@Z; Microsoft::WRL::ComPtr<IStream>::operator=(IStream *)
0x1800f8997  mov     rdx, [rsi]; struct IStream *
0x1800f899a  mov     rcx, [rsp+38h+arg_10]; struct IStream *
0x1800f899f  call    ?CreateDiagnosticData@@YAJPEAUIStream@@0@Z; CreateDiagnosticData(IStream *,IStream *)
0x1800f89a4  mov     ebx, eax
0x1800f89a6  test    eax, eax
0x1800f89a8  jns     short loc_1800F89B1
0x1800f89aa  mov     edx, 37h ; '7'
0x1800f89af  jmp     short loc_1800F895B
0x1800f89b1  mov     ebx, ebp
0x1800f89b3  lea     rcx, [rsp+38h+arg_10]
0x1800f89b8  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x1800f89bd  mov     eax, ebx
0x1800f89bf  mov     rbx, [rsp+38h+arg_0]
0x1800f89c4  mov     rbp, [rsp+38h+arg_8]
0x1800f89c9  add     rsp, 20h
0x1800f89cd  pop     r14
0x1800f89cf  pop     rdi
0x1800f89d0  pop     rsi
0x1800f89d1  retn
```
