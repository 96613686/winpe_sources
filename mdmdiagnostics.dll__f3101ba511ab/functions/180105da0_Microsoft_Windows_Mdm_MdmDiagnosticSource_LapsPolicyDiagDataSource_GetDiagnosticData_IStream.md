# Microsoft::Windows::Mdm::MdmDiagnosticSource::LapsPolicyDiagDataSource::GetDiagnosticData(IStream * *)

- ea: `0x180105da0`
- end: `0x180105e6a`
- name: `?GetDiagnosticData@LapsPolicyDiagDataSource@MdmDiagnosticSource@Mdm@Windows@Microsoft@@UEAAJPEAPEAUIStream@@@Z`
- size: `202`
- prototype: `int(Microsoft::Windows::Mdm::MdmDiagnosticSource::LapsPolicyDiagDataSource *__hidden this, struct IStream **)`
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x1800eb1ac`
- `0x1800ed46c`
- `0x1800f8e70`
- `0x1800f962c`
- `0x180105da0`
- `0x180123aa8`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x180105dc9`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x180105dc9`
- `api-ms-win-shcore-stream-l1-1-0!SHCreateMemStream` at `0x180105e1d`
- `api-ms-win-shcore-stream-l1-1-0!SHCreateMemStream` at `0x180105e1d`

## string_xrefs

- `0x180105e16`: `<?xml version="1.0" encoding="utf-16"?>\n<DiagData>\n  <DataSource name="LAPS">\n    <Key>\n      <Category>Laps_CSP_Policy</Category>\n      <Path>HKLM\Software\Microsoft\Policies\LAPS</Path>\n      <Representation>Type</Representation>\n      <Value>\n        <Name>*</Name>\n        <ValueRepresentation>*</ValueRepresentation>\n      </Value>\n      <Key>\n        <Category>PolicySource</Category>\n        <Path>*</Path>\n        <Representation>Source</Representation>\n      </Key>\n    </Key`
- `0x180105e04`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\dll\lapspolicydiagdata.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Microsoft::Windows::Mdm::MdmDiagnosticSource::LapsPolicyDiagDataSource::GetDiagnosticData(
        Microsoft::Windows::Mdm::MdmDiagnosticSource::LapsPolicyDiagDataSource *this,
        struct IStream **a2)
{
  HRESULT StreamOnHGlobal; // eax
  unsigned __int64 v4; // rdx
  unsigned int v5; // ebx
  __int64 v6; // rdx
  IStream *v7; // rax
  int v9; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  struct IStream *v11; // [rsp+40h] [rbp+18h] BYREF
  unsigned __int64 cbInit; // [rsp+48h] [rbp+20h] BYREF

  v11 = 0;
  cbInit = 0;
  StreamOnHGlobal = CreateStreamOnHGlobal(0, 1, a2);
  v5 = StreamOnHGlobal;
  if ( StreamOnHGlobal >= 0 )
  {
    StreamOnHGlobal = ULongLongMult(0xA94u, v4, &cbInit);
    v5 = StreamOnHGlobal;
    if ( StreamOnHGlobal >= 0 )
    {
      v7 = SHCreateMemStream(
             L"<?xml version=\"1.0\" encoding=\"utf-16\"?>\n"
              "<DiagData>\n"
              "  <DataSource name=\"LAPS\">\n"
              "    <Key>\n"
              "      <Category>Laps_CSP_Policy</Category>\n"
              "      <Path>HKLM\\Software\\Microsoft\\Policies\\LAPS</Path>\n"
              "      <Representation>Type</Representation>\n"
              "      <Value>\n"
              "        <Name>*</Name>\n"
              "        <ValueRepresentation>*</ValueRepresentation>\n"
              "      </Value>\n"
              "      <Key>\n"
              "        <Category>PolicySource</Category>\n"
              "        <Path>*</Path>\n"
              "        <Representation>Source</Representation>\n"
              "      </Key>\n"
              "    </Key>\n"
              "    <Key>\n"
              "      <Category>Laps_GPO_Policy</Category>\n"
              "      <Path>HKLM\\Software\\Microsoft\\Windows\\CurrentVersion\\Policies\\LAPS</Path>\n"
              "      <Representation>Type</Representation>\n"
              "      <Value>\n"
              "        <Name>*</Name>\n"
              "        <ValueRepresentation>*</ValueRepresentation>\n"
              "      </Value>\n"
              "      <Key>\n"
              "        <Category>PolicySource</Category>\n"
              "        <Path>*</Path>\n"
              "        <Representation>Source</Representation>\n"
              "      </Key>\n"
              "    </Key>\n"
              "    <Key>\n"
              "      <Category>Laps_Local_Policy</Category>\n"
              "      <Path>HKLM\\Software\\Microsoft\\Windows\\CurrentVersion\\LAPS\\Config</Path>\n"
              "      <Representation>Type</Representation>\n"
              "      <Value>\n"
              "        <Name>*</Name>\n"
              "        <ValueRepresentation>*</ValueRepresentation>\n"
              "      </Value>\n"
              "      <Key>\n"
              "        <Category>PolicySource</Category>\n"
              "        <Path>*</Path>\n"
              "        <Representation>Source</Representation>\n"
              "      </Key>\n"
              "    </Key>\n"
              "    <Key>\n"
              "      <Category>Laps_Local_State</Category>\n"
              "      <Path>HKLM\\Software\\Microsoft\\Windows\\CurrentVersion\\LAPS\\State</Path>\n"
              "      <Representation>Type</Representation>\n"
              "      <Value>\n"
              "        <Name>*</Name>\n"
              "        <ValueRepresentation>*</ValueRepresentation>\n"
              "      </Value>\n"
              "      <Key>\n"
              "        <Category>PolicySource</Category>\n"
              "        <Path>*</Path>\n"
              "        <Representation>Source</Representation>\n"
              "      </Key>\n"
              "    </Key>\n"
              "    <Key>\n"
              "      <Category>Legacy_Laps_Policy</Category>\n"
              "      <Path>HKLM\\Software\\Policies\\Microsoft Services\\AdmPwd</Path>\n"
              "      <Representation>Type</Representation>\n"
              "      <Value>\n"
              "        <Name>*</Name>\n"
              "        <ValueRepresentation>*</ValueRepresentation>\n"
              "      </Value>\n"
              "      <Key>\n"
              "        <Category>PolicySource</Category>\n"
              "        <Path>*</Path>\n"
              "        <Representation>Source</Representation>\n"
              "      </Key>\n"
              "    </Key>\n"
              "    <Key>\n"
              "      <Category>Legacy_Laps_CSE</Category>\n"
              "      <Path>HKLM\\Software\\Microsoft\\Windows NT\\CurrentVersion\\Winlogon\\GPExtensions\\{D76B9641-3288-"
              "4f75-942D-087DE603E3EA}</Path>\n"
              "      <Representation>Type</Representation>\n"
              "      <Value>\n"
              "        <Name>*</Name>\n"
              "        <ValueRepresentation>*</ValueRepresentation>\n"
              "      </Value>\n"
              "      <Key>\n"
              "        <Category>PolicySource</Category>\n"
              "        <Path>*</Path>\n"
              "        <Representation>Source</Representation>\n"
              "      </Key>\n"
              "    </Key>\n"
              "  </DataSource>\n"
              "</DiagData>",
             cbInit);
      Microsoft::WRL::ComPtr<IStream>::operator=(&v11, v7);
      StreamOnHGlobal = CreateDiagnosticData(v11, *a2);
      v5 = StreamOnHGlobal;
      if ( StreamOnHGlobal >= 0 )
      {
        v5 = 0;
        goto LABEL_9;
      }
      v6 = 74;
    }
    else
    {
      v6 = 68;
    }
  }
  else
  {
    v6 = 67;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v6,
    (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmdiagnostics\\dll\\lapspolicydiagdata.cpp",
    (const char *)(unsigned int)StreamOnHGlobal,
    v9);
LABEL_9:
  Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&v11);
  return v5;
}

```

## disassembly

```asm
0x180105da0  mov     [rsp+arg_0], rbx
0x180105da5  push    rdi; int
0x180105da6  sub     rsp, 20h
0x180105daa  mov     rdi, rdx
0x180105dad  mov     [rsp+28h+arg_10], 0
0x180105db6  mov     [rsp+28h+cbInit], 0
0x180105dbf  mov     r8, rdx; ppstm
0x180105dc2  mov     edx, 1; fDeleteOnRelease
0x180105dc7  xor     ecx, ecx; hGlobal
0x180105dc9  call    cs:__imp_CreateStreamOnHGlobal
0x180105dd0  nop     dword ptr [rax+rax+00h]
0x180105dd5  mov     ebx, eax
0x180105dd7  test    eax, eax
0x180105dd9  jns     short loc_180105DE2
0x180105ddb  mov     edx, 43h ; 'C'
0x180105de0  jmp     short loc_180105DFC
0x180105de2  lea     r8, [rsp+28h+cbInit]; unsigned __int64 *
0x180105de7  mov     ecx, 0A94h; unsigned __int64
0x180105dec  call    ?ULongLongMult@@YAJ_K0PEA_K@Z; ULongLongMult(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x180105df1  mov     ebx, eax
0x180105df3  test    eax, eax
0x180105df5  jns     short loc_180105E12
0x180105df7  mov     edx, 44h ; 'D'; void *
0x180105dfc  mov     rcx, [rsp+28h]; this
0x180105e01  mov     r9d, eax; char *
0x180105e04  lea     r8, aOnecoreuapAdmi_9; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x180105e0b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180105e10  jmp     short loc_180105E52
0x180105e12  mov     edx, dword ptr [rsp+28h+cbInit]; cbInit
0x180105e16  lea     rcx, aXmlVersion10En_8; "<?xml version=\"1.0\" encoding=\"utf-16"...
0x180105e1d  call    cs:__imp_SHCreateMemStream
0x180105e24  nop     dword ptr [rax+rax+00h]
0x180105e29  mov     rdx, rax
0x180105e2c  lea     rcx, [rsp+28h+arg_10]
0x180105e31  call    ??4?$ComPtr@UIStream@@@WRL@Microsoft@@QEAAAEAV012@PEAUIStream@@@Z; Microsoft::WRL::ComPtr<IStream>::operator=(IStream *)
0x180105e36  mov     rdx, [rdi]; struct IStream *
0x180105e39  mov     rcx, [rsp+28h+arg_10]; struct IStream *
0x180105e3e  call    ?CreateDiagnosticData@@YAJPEAUIStream@@0@Z; CreateDiagnosticData(IStream *,IStream *)
0x180105e43  mov     ebx, eax
0x180105e45  test    eax, eax
0x180105e47  jns     short loc_180105E50
0x180105e49  mov     edx, 4Ah ; 'J'
0x180105e4e  jmp     short loc_180105DFC
0x180105e50  xor     ebx, ebx
0x180105e52  lea     rcx, [rsp+28h+arg_10]
0x180105e57  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x180105e5c  mov     eax, ebx
0x180105e5e  mov     rbx, [rsp+28h+arg_0]
0x180105e63  add     rsp, 20h
0x180105e67  pop     rdi
0x180105e68  retn
```
