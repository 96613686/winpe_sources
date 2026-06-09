# Microsoft::Windows::Mdm::MdmDiagnosticSource::LapsPolicyDiagDataSource::GetDiagnosticData(IStream * *)

- ea: `0x180104af0`
- end: `0x180104bad`
- name: `?GetDiagnosticData@LapsPolicyDiagDataSource@MdmDiagnosticSource@Mdm@Windows@Microsoft@@UEAAJPEAPEAUIStream@@@Z`
- size: `189`
- prototype: `__int64 __fastcall(Microsoft::Windows::Mdm::MdmDiagnosticSource::LapsPolicyDiagDataSource *this, struct IStream **)`
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x1800ead14`
- `0x1800ece5c`
- `0x1800f7f10`
- `0x1800f8680`
- `0x180104af0`
- `0x180122018`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x180104b19`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x180104b19`
- `api-ms-win-shcore-stream-l1-1-0!SHCreateMemStream` at `0x180104b67`
- `api-ms-win-shcore-stream-l1-1-0!SHCreateMemStream` at `0x180104b67`

## string_xrefs

- `0x180104b60`: `<?xml version="1.0" encoding="utf-16"?>\n<DiagData>\n  <DataSource name="LAPS">\n    <Key>\n      <Category>Laps_CSP_Policy</Category>\n      <Path>HKLM\Software\Microsoft\Policies\LAPS</Path>\n      <Representation>Type</Representation>\n      <Value>\n        <Name>*</Name>\n        <ValueRepresentation>*</ValueRepresentation>\n      </Value>\n      <Key>\n        <Category>PolicySource</Category>\n        <Path>*</Path>\n        <Representation>Source</Representation>\n      </Key>\n    </Key`
- `0x180104b4e`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\dll\lapspolicydiagdata.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
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
0x180104af0  mov     [rsp+arg_0], rbx
0x180104af5  push    rdi; int
0x180104af6  sub     rsp, 20h
0x180104afa  mov     rdi, rdx
0x180104afd  mov     [rsp+28h+arg_10], 0
0x180104b06  mov     [rsp+28h+cbInit], 0
0x180104b0f  mov     r8, rdx; ppstm
0x180104b12  mov     edx, 1; fDeleteOnRelease
0x180104b17  xor     ecx, ecx; hGlobal
0x180104b19  call    cs:__imp_CreateStreamOnHGlobal
0x180104b1f  mov     ebx, eax
0x180104b21  test    eax, eax
0x180104b23  jns     short loc_180104B2C
0x180104b25  mov     edx, 43h ; 'C'
0x180104b2a  jmp     short loc_180104B46
0x180104b2c  lea     r8, [rsp+28h+cbInit]; unsigned __int64 *
0x180104b31  mov     ecx, 0A94h; unsigned __int64
0x180104b36  call    ?ULongLongMult@@YAJ_K0PEA_K@Z; ULongLongMult(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x180104b3b  mov     ebx, eax
0x180104b3d  test    eax, eax
0x180104b3f  jns     short loc_180104B5C
0x180104b41  mov     edx, 44h ; 'D'; void *
0x180104b46  mov     rcx, [rsp+28h]; this
0x180104b4b  mov     r9d, eax; char *
0x180104b4e  lea     r8, aOnecoreuapAdmi_9; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x180104b55  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180104b5a  jmp     short loc_180104B96
0x180104b5c  mov     edx, dword ptr [rsp+28h+cbInit]; cbInit
0x180104b60  lea     rcx, aXmlVersion10En_8; "<?xml version=\"1.0\" encoding=\"utf-16"...
0x180104b67  call    cs:__imp_SHCreateMemStream
0x180104b6d  mov     rdx, rax
0x180104b70  lea     rcx, [rsp+28h+arg_10]
0x180104b75  call    ??4?$ComPtr@UIStream@@@WRL@Microsoft@@QEAAAEAV012@PEAUIStream@@@Z; Microsoft::WRL::ComPtr<IStream>::operator=(IStream *)
0x180104b7a  mov     rdx, [rdi]; struct IStream *
0x180104b7d  mov     rcx, [rsp+28h+arg_10]; struct IStream *
0x180104b82  call    ?CreateDiagnosticData@@YAJPEAUIStream@@0@Z; CreateDiagnosticData(IStream *,IStream *)
0x180104b87  mov     ebx, eax
0x180104b89  test    eax, eax
0x180104b8b  jns     short loc_180104B94
0x180104b8d  mov     edx, 4Ah ; 'J'
0x180104b92  jmp     short loc_180104B46
0x180104b94  xor     ebx, ebx
0x180104b96  lea     rcx, [rsp+28h+arg_10]
0x180104b9b  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x180104ba0  mov     eax, ebx
0x180104ba2  mov     rbx, [rsp+28h+arg_0]
0x180104ba7  add     rsp, 20h
0x180104bab  pop     rdi
0x180104bac  retn
```
