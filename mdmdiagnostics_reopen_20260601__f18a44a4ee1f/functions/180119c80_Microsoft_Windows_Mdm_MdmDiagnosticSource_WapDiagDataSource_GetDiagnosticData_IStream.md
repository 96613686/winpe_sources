# Microsoft::Windows::Mdm::MdmDiagnosticSource::WapDiagDataSource::GetDiagnosticData(IStream * *)

- ea: `0x180119c80`
- end: `0x180119d8b`
- name: `?GetDiagnosticData@WapDiagDataSource@MdmDiagnosticSource@Mdm@Windows@Microsoft@@UEAAJPEAPEAUIStream@@@Z`
- size: `267`
- prototype: `int(Microsoft::Windows::Mdm::MdmDiagnosticSource::WapDiagDataSource *__hidden this, struct IStream **)`
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x1800eb1ac`
- `0x1800ed46c`
- `0x1800f8e70`
- `0x1800f962c`
- `0x180119c80`
- `0x180123aa8`

## import_xrefs

- `ntdll!RtlIsStateSeparationEnabled` at `0x180119cbf`
- `ntdll!RtlIsStateSeparationEnabled` at `0x180119d1d`
- `ntdll!RtlIsStateSeparationEnabled` at `0x180119cbf`
- `ntdll!RtlIsStateSeparationEnabled` at `0x180119d1d`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x180119ca8`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x180119ca8`
- `api-ms-win-shcore-stream-l1-1-0!SHCreateMemStream` at `0x180119d36`
- `api-ms-win-shcore-stream-l1-1-0!SHCreateMemStream` at `0x180119d36`

## string_xrefs

- `0x180119cd2`: `<?xml version="1.0" encoding="utf-16"?>\n<DiagData>\n  <DataSource name="OSDataWAP">\n    <Key>\n      <Category>Bootstrap</Category>\n      <Path>HKLM\OSData\Software\Microsoft\WAP\*</Path>\n      <Representation>Type</Representation>\n      <Value>\n        <Name>*</Name>\n        <ValueRepresentation>*</ValueRepresentation>\n      </Value>\n      <Key>\n        <Category>Proxy</Category>\n        <Path>*</Path>\n        <Representation>Name</Representation>\n        <Value>\n          <Name>*`
- `0x180119ccb`: `<?xml version="1.0" encoding="utf-16"?>\n<DiagData>\n  <DataSource name="WAP">\n    <Key>\n      <Category>Bootstrap</Category>\n      <Path>HKLM\Software\Microsoft\WAP\*</Path>\n      <Representation>Type</Representation>\n      <Value>\n        <Name>*</Name>\n        <ValueRepresentation>*</ValueRepresentation>\n      </Value>\n      <Key>\n        <Category>Proxy</Category>\n        <Path>*</Path>\n        <Representation>Name</Representation>\n        <Value>\n          <Name>*</Name>\n    `
- `0x180119d0f`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\dll\wapdiagdata.cpp`

## pseudocode

```c
__int64 __fastcall Microsoft::Windows::Mdm::MdmDiagnosticSource::WapDiagDataSource::GetDiagnosticData(
        Microsoft::Windows::Mdm::MdmDiagnosticSource::WapDiagDataSource *this,
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
                        "  <DataSource name=\"OSDataWAP\">\n"
                        "    <Key>\n"
                        "      <Category>Bootstrap</Category>\n"
                        "      <Path>HKLM\\OSData\\Software\\Microsoft\\WAP\\*</Path>\n"
                        "      <Representation>Type</Representation>\n"
                        "      <Value>\n"
                        "        <Name>*</Name>\n"
                        "        <ValueRepresentation>*</ValueRepresentation>\n"
                        "      </Value>\n"
                        "      <Key>\n"
                        "        <Category>Proxy</Category>\n"
                        "        <Path>*</Path>\n"
                        "        <Representation>Name</Representation>\n"
                        "        <Value>\n"
                        "          <Name>*</Name>\n"
                        "          <ValueRepresentation>*</ValueRepresentation>\n"
                        "        </Value>\n"
                        "        <Key>\n"
                        "          <Category>ProxyName</Category>\n"
                        "          <Path>*</Path>\n"
                        "          <Representation>Name</Representation>\n"
                        "          <Value>\n"
                        "            <Name>*</Name>\n"
                        "            <ValueRepresentation>*</ValueRepresentation>\n"
                        "          </Value>\n"
                        "        </Key>\n"
                        "      </Key>\n"
                        "    </Key>\n"
                        "    <Key>\n"
                        "      <Category>SecurityPolicies</Category>\n"
                        "      <Path>HKLM\\OSData\\Software\\Microsoft\\Policies\\*</Path>\n"
                        "      <Representation>Area</Representation>\n"
                        "      <Value>\n"
                        "        <Name>00001008</Name>\n"
                        "        <ValueRepresentation>SECPOLICY_TPSCARRIERROLE</ValueRepresentation>\n"
                        "      </Value>\n"
                        "      <Value>\n"
                        "        <Name>00001009</Name>\n"
                        "        <ValueRepresentation>SECPOLICY_MAXAUTHENTICATIONRETRY</ValueRepresentation>\n"
                        "      </Value>\n"
                        "      <Value>\n"
                        "        <Name>0000100c</Name>\n"
                        "        <ValueRepresentation>SECPOLICY_SL_MESSAGE</ValueRepresentation>\n"
                        "      </Value>\n"
                        "      <Value>\n"
                        "        <Name>0000100d</Name>\n"
                        "        <ValueRepresentation>SECPOLICY_SI_MESSAGE</ValueRepresentation>\n"
                        "      </Value>\n"
                        "      <Value>\n"
                        "        <Name>0000100e</Name>\n"
                        "        <ValueRepresentation>SECPOLICY_UNAUTHMESSAGES</ValueRepresentation>\n"
                        "      </Value>\n"
                        "      <Value>\n"
                        "        <Name>0000100f</Name>\n"
                        "        <ValueRepresentation>SECPOLICY_OTAPROVISIONING</ValueRepresentation>\n"
                        "      </Value>\n"
                        "      <Value>\n"
                        "        <Name>00001011</Name>\n"
                        "        <ValueRepresentation>SECPOLICY_WSPNOTIFICATIONS</ValueRepresentation>\n"
                        "      </Value>\n"
                        "      <Value>\n"
                        "        <Name>00001019</Name>\n"
                        "        <ValueRepresentation>SECPOLICY_TRUSTED_WAP_PROXY</ValueRepresentation>\n"
                        "      </Value>\n"
                        "      <Value>\n"
                        "        <Name>00001024</Name>\n"
                        "        <ValueRepresentation>SECPOLICY_WAP_NETWPIN_PROMPT</ValueRepresentation>\n"
                        "      </Value>\n"
                        "      <Value>\n"
                        "        <Name>0000102d</Name>\n"
                        "        <ValueRepresentation>SECPOLICY_OMACPNETWPINMSG</ValueRepresentation>\n"
                        "      </Value>\n"
                        "      <Value>\n"
                        "        <Name>0000102e</Name>\n"
                        "        <ValueRepresentation>SECPOLICY_OMACPUSERPINMSG</ValueRepresentation>\n"
                        "      </Value>\n"
                        "      <Value>\n"
                        "        <Name>0000102f</Name>\n"
                        "        <ValueRepresentation>SECPOLICY_OMACPUSERNETWPINMSG</ValueRepresentation>\n"
                        "      </Value>\n"
                        "      <Value>\n"
                        "        <Name>00001009</Name>\n"
                        "        <ValueRepresentation>SECPOLICY_MAXAUTHENTICATIONRETRY</ValueRepresentation>\n"
                        "      </Value>\n"
                        "      <Value>\n"
                        "        <Name>00001030</Name>\n"
                        "        <ValueRepresentation>SECPOLICY_MMS_MESSAGE</ValueRepresentation>\n"
                        "      </Value>\n"
                        "    </Key>\n"
                        "  </DataSource>\n"
                        "</DiagData>";
    v8 = L"<?xml version=\"1.0\" encoding=\"utf-16\"?>\n"
          "<DiagData>\n"
          "  <DataSource name=\"OSDataWAP\">\n"
          "    <Key>\n"
          "      <Category>Bootstrap</Category>\n"
          "      <Path>HKLM\\OSData\\Software\\Microsoft\\WAP\\*</Path>\n"
          "      <Representation>Type</Representation>\n"
          "      <Value>\n"
          "        <Name>*</Name>\n"
          "        <ValueRepresentation>*</ValueRepresentation>\n"
          "      </Value>\n"
          "      <Key>\n"
          "        <Category>Proxy</Category>\n"
          "        <Path>*</Path>\n"
          "        <Representation>Name</Representation>\n"
          "        <Value>\n"
          "          <Name>*</Name>\n"
          "          <ValueRepresentation>*</ValueRepresentation>\n"
          "        </Value>\n"
          "        <Key>\n"
          "          <Category>ProxyName</Category>\n"
          "          <Path>*</Path>\n"
          "          <Representation>Name</Representation>\n"
          "          <Value>\n"
          "            <Name>*</Name>\n"
          "            <ValueRepresentation>*</ValueRepresentation>\n"
          "          </Value>\n"
          "        </Key>\n"
          "      </Key>\n"
          "    </Key>\n"
          "    <Key>\n"
          "      <Category>SecurityPolicies</Category>\n"
          "      <Path>HKLM\\OSData\\Software\\Microsoft\\Policies\\*</Path>\n"
          "      <Representation>Area</Representation>\n"
          "      <Value>\n"
          "        <Name>00001008</Name>\n"
          "        <ValueRepresentation>SECPOLICY_TPSCARRIERROLE</ValueRepresentation>\n"
          "      </Value>\n"
          "      <Value>\n"
          "        <Name>00001009</Name>\n"
          "        <ValueRepresentation>SECPOLICY_MAXAUTHENTICATIONRETRY</ValueRepresentation>\n"
          "      </Value>\n"
          "      <Value>\n"
          "        <Name>0000100c</Name>\n"
          "        <ValueRepresentation>SECPOLICY_SL_MESSAGE</ValueRepresentation>\n"
          "      </Value>\n"
          "      <Value>\n"
          "        <Name>0000100d</Name>\n"
          "        <ValueRepresentation>SECPOLICY_SI_MESSAGE</ValueRepresentation>\n"
          "      </Value>\n"
          "      <Value>\n"
          "        <Name>0000100e</Name>\n"
          "        <ValueRepresentation>SECPOLICY_UNAUTHMESSAGES</ValueRepresentation>\n"
          "      </Value>\n"
          "      <Value>\n"
          "        <Name>0000100f</Name>\n"
          "        <ValueRepresentation>SECPOLICY_OTAPROVISIONING</ValueRepresentation>\n"
          "      </Value>\n"
          "      <Value>\n"
          "        <Name>00001011</Name>\n"
          "        <ValueRepresentation>SECPOLICY_WSPNOTIFICATIONS</ValueRepresentation>\n"
          "      </Value>\n"
          "      <Value>\n"
          "        <Name>00001019</Name>\n"
          "        <ValueRepresentation>SECPOLICY_TRUSTED_WAP_PROXY</ValueRepresentation>\n"
          "      </Value>\n"
          "      <Value>\n"
          "        <Name>00001024</Name>\n"
          "        <ValueRepresentation>SECPOLICY_WAP_NETWPIN_PROMPT</ValueRepresentation>\n"
          "      </Value>\n"
          "      <Value>\n"
          "        <Name>0000102d</Name>\n"
          "        <ValueRepresentation>SECPOLICY_OMACPNETWPINMSG</ValueRepresentation>\n"
          "      </Value>\n"
          "      <Value>\n"
          "        <Name>0000102e</Name>\n"
          "        <ValueRepresentation>SECPOLICY_OMACPUSERPINMSG</ValueRepresentation>\n"
          "      </Value>\n"
          "      <Value>\n"
          "        <Name>0000102f</Name>\n"
          "        <ValueRepresentation>SECPOLICY_OMACPUSERNETWPINMSG</ValueRepresentation>\n"
          "      </Value>\n"
          "      <Value>\n"
          "        <Name>00001009</Name>\n"
          "        <ValueRepresentation>SECPOLICY_MAXAUTHENTICATIONRETRY</ValueRepresentation>\n"
          "      </Value>\n"
          "      <Value>\n"
          "        <Name>00001030</Name>\n"
          "        <ValueRepresentation>SECPOLICY_MMS_MESSAGE</ValueRepresentation>\n"
          "      </Value>\n"
          "    </Key>\n"
          "  </DataSource>\n"
          "</DiagData>";
    if ( !IsStateSeparationEnabled )
      v8 = (const wchar_t *)L"<?xml version=\"1.0\" encoding=\"utf-16\"?>\n"
                             "<DiagData>\n"
                             "  <DataSource name=\"WAP\">\n"
                             "    <Key>\n"
                             "      <Category>Bootstrap</Category>\n"
                             "      <Path>HKLM\\Software\\Microsoft\\WAP\\*</Path>\n"
                             "      <Representation>Type</Representation>\n"
                             "      <Value>\n"
                             "        <Name>*</Name>\n"
                             "        <ValueRepresentation>*</ValueRepresentation>\n"
                             "      </Value>\n"
                             "      <Key>\n"
                             "        <Category>Proxy</Category>\n"
                             "        <Path>*</Path>\n"
                             "        <Representation>Name</Representation>\n"
                             "        <Value>\n"
                             "          <Name>*</Name>\n"
                             "          <ValueRepresentation>*</ValueRepresentation>\n"
                             "        </Value>\n"
                             "        <Key>\n"
                             "          <Category>ProxyName</Category>\n"
                             "          <Path>*</Path>\n"
                             "          <Representation>Name</Representation>\n"
                             "          <Value>\n"
                             "            <Name>*</Name>\n"
                             "            <ValueRepresentation>*</ValueRepresentation>\n"
                             "          </Value>\n"
                             "        </Key>\n"
                             "      </Key>\n"
                             "    </Key>\n"
                             "    <Key>\n"
                             "      <Category>SecurityPolicies</Category>\n"
                             "      <Path>HKLM\\Software\\Microsoft\\Policies\\*</Path>\n"
                             "      <Representation>Area</Representation>\n"
                             "      <Value>\n"
                             "        <Name>00001008</Name>\n"
                             "        <ValueRepresentation>SECPOLICY_TPSCARRIERROLE</ValueRepresentation>\n"
                             "      </Value>\n"
                             "      <Value>\n"
                             "        <Name>00001009</Name>\n"
                             "        <ValueRepresentation>SECPOLICY_MAXAUTHENTICATIONRETRY</ValueRepresentation>\n"
                             "      </Value>\n"
                             "      <Value>\n"
                             "        <Name>0000100c</Name>\n"
                             "        <ValueRepresentation>SECPOLICY_SL_MESSAGE</ValueRepresentation>\n"
                             "      </Value>\n"
                             "      <Value>\n"
                             "        <Name>0000100d</Name>\n"
                             "        <ValueRepresentation>SECPOLICY_SI_MESSAGE</ValueRepresentation>\n"
                             "      </Value>\n"
                             "      <Value>\n"
                             "        <Name>0000100e</Name>\n"
                             "        <ValueRepresentation>SECPOLICY_UNAUTHMESSAGES</ValueRepresentation>\n"
                             "      </Value>\n"
                             "      <Value>\n"
                             "        <Name>0000100f</Name>\n"
                             "        <ValueRepresentation>SECPOLICY_OTAPROVISIONING</ValueRepresentation>\n"
                             "      </Value>\n"
                             "      <Value>\n"
                             "        <Name>00001011</Name>\n"
                             "        <ValueRepresentation>SECPOLICY_WSPNOTIFICATIONS</ValueRepresentation>\n"
                             "      </Value>\n"
                             "      <Value>\n"
                             "        <Name>00001019</Name>\n"
                             "        <ValueRepresentation>SECPOLICY_TRUSTED_WAP_PROXY</ValueRepresentation>\n"
                             "      </Value>\n"
                             "      <Value>\n"
                             "        <Name>00001024</Name>\n"
                             "        <ValueRepresentation>SECPOLICY_WAP_NETWPIN_PROMPT</ValueRepresentation>\n"
                             "      </Value>\n"
                             "      <Value>\n"
                             "        <Name>0000102d</Name>\n"
                             "        <ValueRepresentation>SECPOLICY_OMACPNETWPINMSG</ValueRepresentation>\n"
                             "      </Value>\n"
                             "      <Value>\n"
                             "        <Name>0000102e</Name>\n"
                             "        <ValueRepresentation>SECPOLICY_OMACPUSERPINMSG</ValueRepresentation>\n"
                             "      </Value>\n"
                             "      <Value>\n"
                             "        <Name>0000102f</Name>\n"
                             "        <ValueRepresentation>SECPOLICY_OMACPUSERNETWPINMSG</ValueRepresentation>\n"
                             "      </Value>\n"
                             "      <Value>\n"
                             "        <Name>00001009</Name>\n"
                             "        <ValueRepresentation>SECPOLICY_MAXAUTHENTICATIONRETRY</ValueRepresentation>\n"
                             "      </Value>\n"
                             "      <Value>\n"
                             "        <Name>00001030</Name>\n"
                             "        <ValueRepresentation>SECPOLICY_MMS_MESSAGE</ValueRepresentation>\n"
                             "      </Value>\n"
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
              "  <DataSource name=\"WAP\">\n"
              "    <Key>\n"
              "      <Category>Bootstrap</Category>\n"
              "      <Path>HKLM\\Software\\Microsoft\\WAP\\*</Path>\n"
              "      <Representation>Type</Representation>\n"
              "      <Value>\n"
              "        <Name>*</Name>\n"
              "        <ValueRepresentation>*</ValueRepresentation>\n"
              "      </Value>\n"
              "      <Key>\n"
              "        <Category>Proxy</Category>\n"
              "        <Path>*</Path>\n"
              "        <Representation>Name</Representation>\n"
              "        <Value>\n"
              "          <Name>*</Name>\n"
              "          <ValueRepresentation>*</ValueRepresentation>\n"
              "        </Value>\n"
              "        <Key>\n"
              "          <Category>ProxyName</Category>\n"
              "          <Path>*</Path>\n"
              "          <Representation>Name</Representation>\n"
              "          <Value>\n"
              "            <Name>*</Name>\n"
              "            <ValueRepresentation>*</ValueRepresentation>\n"
              "          </Value>\n"
              "        </Key>\n"
              "      </Key>\n"
              "    </Key>\n"
              "    <Key>\n"
              "      <Category>SecurityPolicies</Category>\n"
              "      <Path>HKLM\\Software\\Microsoft\\Policies\\*</Path>\n"
              "      <Representation>Area</Representation>\n"
              "      <Value>\n"
              "        <Name>00001008</Name>\n"
              "        <ValueRepresentation>SECPOLICY_TPSCARRIERROLE</ValueRepresentation>\n"
              "      </Value>\n"
              "      <Value>\n"
              "        <Name>00001009</Name>\n"
              "        <ValueRepresentation>SECPOLICY_MAXAUTHENTICATIONRETRY</ValueRepresentation>\n"
              "      </Value>\n"
              "      <Value>\n"
              "        <Name>0000100c</Name>\n"
              "        <ValueRepresentation>SECPOLICY_SL_MESSAGE</ValueRepresentation>\n"
              "      </Value>\n"
              "      <Value>\n"
              "        <Name>0000100d</Name>\n"
              "        <ValueRepresentation>SECPOLICY_SI_MESSAGE</ValueRepresentation>\n"
              "      </Value>\n"
              "      <Value>\n"
              "        <Name>0000100e</Name>\n"
              "        <ValueRepresentation>SECPOLICY_UNAUTHMESSAGES</ValueRepresentation>\n"
              "      </Value>\n"
              "      <Value>\n"
              "        <Name>0000100f</Name>\n"
              "        <ValueRepresentation>SECPOLICY_OTAPROVISIONING</ValueRepresentation>\n"
              "      </Value>\n"
              "      <Value>\n"
              "        <Name>00001011</Name>\n"
              "        <ValueRepresentation>SECPOLICY_WSPNOTIFICATIONS</ValueRepresentation>\n"
              "      </Value>\n"
              "      <Value>\n"
              "        <Name>00001019</Name>\n"
              "        <ValueRepresentation>SECPOLICY_TRUSTED_WAP_PROXY</ValueRepresentation>\n"
              "      </Value>\n"
              "      <Value>\n"
              "        <Name>00001024</Name>\n"
              "        <ValueRepresentation>SECPOLICY_WAP_NETWPIN_PROMPT</ValueRepresentation>\n"
              "      </Value>\n"
              "      <Value>\n"
              "        <Name>0000102d</Name>\n"
              "        <ValueRepresentation>SECPOLICY_OMACPNETWPINMSG</ValueRepresentation>\n"
              "      </Value>\n"
              "      <Value>\n"
              "        <Name>0000102e</Name>\n"
              "        <ValueRepresentation>SECPOLICY_OMACPUSERPINMSG</ValueRepresentation>\n"
              "      </Value>\n"
              "      <Value>\n"
              "        <Name>0000102f</Name>\n"
              "        <ValueRepresentation>SECPOLICY_OMACPUSERNETWPINMSG</ValueRepresentation>\n"
              "      </Value>\n"
              "      <Value>\n"
              "        <Name>00001009</Name>\n"
              "        <ValueRepresentation>SECPOLICY_MAXAUTHENTICATIONRETRY</ValueRepresentation>\n"
              "      </Value>\n"
              "      <Value>\n"
              "        <Name>00001030</Name>\n"
              "        <ValueRepresentation>SECPOLICY_MMS_MESSAGE</ValueRepresentation>\n"
              "      </Value>\n"
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
    (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmdiagnostics\\dll\\wapdiagdata.cpp",
    (const char *)(unsigned int)StreamOnHGlobal,
    v12);
LABEL_15:
  Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&v14);
  return v4;
}

```

## disassembly

```asm
0x180119c80  mov     rax, rsp
0x180119c83  mov     [rax+8], rbx
0x180119c87  mov     [rax+10h], rbp
0x180119c8b  push    rsi
0x180119c8c  push    rdi
0x180119c8d  push    r14; int
0x180119c8f  sub     rsp, 20h
0x180119c93  mov     rsi, rdx
0x180119c96  xor     ebp, ebp
0x180119c98  mov     [rax+18h], rbp
0x180119c9c  mov     [rax+20h], rbp
0x180119ca0  mov     r8, rdx; ppstm
0x180119ca3  lea     edx, [rbp+1]; fDeleteOnRelease
0x180119ca6  xor     ecx, ecx; hGlobal
0x180119ca8  call    cs:__imp_CreateStreamOnHGlobal
0x180119caf  nop     dword ptr [rax+rax+00h]
0x180119cb4  mov     ebx, eax
0x180119cb6  test    eax, eax
0x180119cb8  jns     short loc_180119CBF
0x180119cba  lea     edx, [rbp+31h]
0x180119cbd  jmp     short loc_180119D07
0x180119cbf  call    cs:__imp_RtlIsStateSeparationEnabled
0x180119cc6  nop     dword ptr [rax+rax+00h]
0x180119ccb  lea     r14, aXmlVersion10En_17; "<?xml version=\"1.0\" encoding=\"utf-16"...
0x180119cd2  lea     rdi, aXmlVersion10En_13; "<?xml version=\"1.0\" encoding=\"utf-16"...
0x180119cd9  mov     rdx, rdi
0x180119cdc  test    al, al
0x180119cde  cmovz   rdx, r14; unsigned __int64
0x180119ce2  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180119ce6  inc     rcx
0x180119ce9  cmp     [rdx+rcx*2], bp
0x180119ced  jnz     short loc_180119CE6
0x180119cef  inc     rcx; unsigned __int64
0x180119cf2  lea     r8, [rsp+38h+cbInit]; unsigned __int64 *
0x180119cf7  call    ?ULongLongMult@@YAJ_K0PEA_K@Z; ULongLongMult(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x180119cfc  mov     ebx, eax
0x180119cfe  test    eax, eax
0x180119d00  jns     short loc_180119D1D
0x180119d02  mov     edx, 32h ; '2'; void *
0x180119d07  mov     rcx, [rsp+38h]; this
0x180119d0c  mov     r9d, eax; char *
0x180119d0f  lea     r8, aOnecoreuapAdmi_18; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x180119d16  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180119d1b  jmp     short loc_180119D6B
0x180119d1d  call    cs:__imp_RtlIsStateSeparationEnabled
0x180119d24  nop     dword ptr [rax+rax+00h]
0x180119d29  test    al, al
0x180119d2b  cmovz   rdi, r14
0x180119d2f  mov     edx, dword ptr [rsp+38h+cbInit]; cbInit
0x180119d33  mov     rcx, rdi; pInit
0x180119d36  call    cs:__imp_SHCreateMemStream
0x180119d3d  nop     dword ptr [rax+rax+00h]
0x180119d42  mov     rdx, rax
0x180119d45  lea     rcx, [rsp+38h+arg_10]
0x180119d4a  call    ??4?$ComPtr@UIStream@@@WRL@Microsoft@@QEAAAEAV012@PEAUIStream@@@Z; Microsoft::WRL::ComPtr<IStream>::operator=(IStream *)
0x180119d4f  mov     rdx, [rsi]; struct IStream *
0x180119d52  mov     rcx, [rsp+38h+arg_10]; struct IStream *
0x180119d57  call    ?CreateDiagnosticData@@YAJPEAUIStream@@0@Z; CreateDiagnosticData(IStream *,IStream *)
0x180119d5c  mov     ebx, eax
0x180119d5e  test    eax, eax
0x180119d60  jns     short loc_180119D69
0x180119d62  mov     edx, 37h ; '7'
0x180119d67  jmp     short loc_180119D07
0x180119d69  mov     ebx, ebp
0x180119d6b  lea     rcx, [rsp+38h+arg_10]
0x180119d70  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x180119d75  mov     eax, ebx
0x180119d77  mov     rbx, [rsp+38h+arg_0]
0x180119d7c  mov     rbp, [rsp+38h+arg_8]
0x180119d81  add     rsp, 20h
0x180119d85  pop     r14
0x180119d87  pop     rdi
0x180119d88  pop     rsi
0x180119d89  retn
```
