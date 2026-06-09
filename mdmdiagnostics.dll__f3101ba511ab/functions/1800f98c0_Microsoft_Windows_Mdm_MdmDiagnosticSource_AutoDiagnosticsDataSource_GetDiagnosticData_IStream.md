# Microsoft::Windows::Mdm::MdmDiagnosticSource::AutoDiagnosticsDataSource::GetDiagnosticData(IStream * *)

- ea: `0x1800f98c0`
- end: `0x1800f99cb`
- name: `?GetDiagnosticData@AutoDiagnosticsDataSource@MdmDiagnosticSource@Mdm@Windows@Microsoft@@UEAAJPEAPEAUIStream@@@Z`
- size: `267`
- prototype: `int(Microsoft::Windows::Mdm::MdmDiagnosticSource::AutoDiagnosticsDataSource *__hidden this, struct IStream **)`
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x1800eb1ac`
- `0x1800ed46c`
- `0x1800f8e70`
- `0x1800f962c`
- `0x1800f98c0`
- `0x180123aa8`

## import_xrefs

- `ntdll!RtlIsStateSeparationEnabled` at `0x1800f98ff`
- `ntdll!RtlIsStateSeparationEnabled` at `0x1800f995d`
- `ntdll!RtlIsStateSeparationEnabled` at `0x1800f98ff`
- `ntdll!RtlIsStateSeparationEnabled` at `0x1800f995d`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x1800f98e8`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x1800f98e8`
- `api-ms-win-shcore-stream-l1-1-0!SHCreateMemStream` at `0x1800f9976`
- `api-ms-win-shcore-stream-l1-1-0!SHCreateMemStream` at `0x1800f9976`

## string_xrefs

- `0x1800f990b`: `<?xml version="1.0" encoding="utf-16"?>\n<DiagData>\n  <DataSource name="Diagnostics">\n    <Key>\n      <Category>ErrorLog</Category>\n      <Path>HKLM\Software\Microsoft\Provisioning\Diagnostics\*</Path>\n      <Representation>Component</Representation>   \n      <Value>\n         <Name>*</Name>\n         <ValueRepresentation>*</ValueRepresentation>\n      </Value>\n      <Key>\n         <Category>SubComponent</Category>\n         <Path>*</Path>\n         <Representation>Name</Representation>\`
- `0x1800f9912`: `<?xml version="1.0" encoding="utf-16"?>\n<DiagData>\n  <DataSource name="OSDataDiagnostics">\n    <Key>\n      <Category>ErrorLog</Category>\n      <Path>HKLM\OSData\Software\Microsoft\Provisioning\Diagnostics\*</Path>\n      <Representation>Component</Representation>   \n      <Value>\n         <Name>*</Name>\n         <ValueRepresentation>*</ValueRepresentation>\n      </Value>\n      <Key>\n         <Category>SubComponent</Category>\n         <Path>*</Path>\n         <Representation>Name</Rep`
- `0x1800f994f`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\dll\diagnosticsdata.cpp`

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
0x1800f98c0  mov     rax, rsp
0x1800f98c3  mov     [rax+8], rbx
0x1800f98c7  mov     [rax+10h], rbp
0x1800f98cb  push    rsi
0x1800f98cc  push    rdi
0x1800f98cd  push    r14; int
0x1800f98cf  sub     rsp, 20h
0x1800f98d3  mov     rsi, rdx
0x1800f98d6  xor     ebp, ebp
0x1800f98d8  mov     [rax+18h], rbp
0x1800f98dc  mov     [rax+20h], rbp
0x1800f98e0  mov     r8, rdx; ppstm
0x1800f98e3  lea     edx, [rbp+1]; fDeleteOnRelease
0x1800f98e6  xor     ecx, ecx; hGlobal
0x1800f98e8  call    cs:__imp_CreateStreamOnHGlobal
0x1800f98ef  nop     dword ptr [rax+rax+00h]
0x1800f98f4  mov     ebx, eax
0x1800f98f6  test    eax, eax
0x1800f98f8  jns     short loc_1800F98FF
0x1800f98fa  lea     edx, [rbp+31h]
0x1800f98fd  jmp     short loc_1800F9947
0x1800f98ff  call    cs:__imp_RtlIsStateSeparationEnabled
0x1800f9906  nop     dword ptr [rax+rax+00h]
0x1800f990b  lea     r14, aXmlVersion10En_14; "<?xml version=\"1.0\" encoding=\"utf-16"...
0x1800f9912  lea     rdi, aXmlVersion10En_24; "<?xml version=\"1.0\" encoding=\"utf-16"...
0x1800f9919  mov     rdx, rdi
0x1800f991c  test    al, al
0x1800f991e  cmovz   rdx, r14; unsigned __int64
0x1800f9922  or      rcx, 0FFFFFFFFFFFFFFFFh
0x1800f9926  inc     rcx
0x1800f9929  cmp     [rdx+rcx*2], bp
0x1800f992d  jnz     short loc_1800F9926
0x1800f992f  inc     rcx; unsigned __int64
0x1800f9932  lea     r8, [rsp+38h+cbInit]; unsigned __int64 *
0x1800f9937  call    ?ULongLongMult@@YAJ_K0PEA_K@Z; ULongLongMult(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x1800f993c  mov     ebx, eax
0x1800f993e  test    eax, eax
0x1800f9940  jns     short loc_1800F995D
0x1800f9942  mov     edx, 32h ; '2'; void *
0x1800f9947  mov     rcx, [rsp+38h]; this
0x1800f994c  mov     r9d, eax; char *
0x1800f994f  lea     r8, aOnecoreuapAdmi_10; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x1800f9956  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800f995b  jmp     short loc_1800F99AB
0x1800f995d  call    cs:__imp_RtlIsStateSeparationEnabled
0x1800f9964  nop     dword ptr [rax+rax+00h]
0x1800f9969  test    al, al
0x1800f996b  cmovz   rdi, r14
0x1800f996f  mov     edx, dword ptr [rsp+38h+cbInit]; cbInit
0x1800f9973  mov     rcx, rdi; pInit
0x1800f9976  call    cs:__imp_SHCreateMemStream
0x1800f997d  nop     dword ptr [rax+rax+00h]
0x1800f9982  mov     rdx, rax
0x1800f9985  lea     rcx, [rsp+38h+arg_10]
0x1800f998a  call    ??4?$ComPtr@UIStream@@@WRL@Microsoft@@QEAAAEAV012@PEAUIStream@@@Z; Microsoft::WRL::ComPtr<IStream>::operator=(IStream *)
0x1800f998f  mov     rdx, [rsi]; struct IStream *
0x1800f9992  mov     rcx, [rsp+38h+arg_10]; struct IStream *
0x1800f9997  call    ?CreateDiagnosticData@@YAJPEAUIStream@@0@Z; CreateDiagnosticData(IStream *,IStream *)
0x1800f999c  mov     ebx, eax
0x1800f999e  test    eax, eax
0x1800f99a0  jns     short loc_1800F99A9
0x1800f99a2  mov     edx, 37h ; '7'
0x1800f99a7  jmp     short loc_1800F9947
0x1800f99a9  mov     ebx, ebp
0x1800f99ab  lea     rcx, [rsp+38h+arg_10]
0x1800f99b0  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x1800f99b5  mov     eax, ebx
0x1800f99b7  mov     rbx, [rsp+38h+arg_0]
0x1800f99bc  mov     rbp, [rsp+38h+arg_8]
0x1800f99c1  add     rsp, 20h
0x1800f99c5  pop     r14
0x1800f99c7  pop     rdi
0x1800f99c8  pop     rsi
0x1800f99c9  retn
```
