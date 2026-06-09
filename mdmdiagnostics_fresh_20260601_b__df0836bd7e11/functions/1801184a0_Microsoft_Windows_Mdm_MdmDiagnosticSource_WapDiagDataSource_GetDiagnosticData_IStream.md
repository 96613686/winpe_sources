# Microsoft::Windows::Mdm::MdmDiagnosticSource::WapDiagDataSource::GetDiagnosticData(IStream * *)

- ea: `0x1801184a0`
- end: `0x180118592`
- name: `?GetDiagnosticData@WapDiagDataSource@MdmDiagnosticSource@Mdm@Windows@Microsoft@@UEAAJPEAPEAUIStream@@@Z`
- size: `242`
- prototype: `int(Microsoft::Windows::Mdm::MdmDiagnosticSource::WapDiagDataSource *__hidden this, struct IStream **)`
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x1800ead14`
- `0x1800ece5c`
- `0x1800f7f10`
- `0x1800f8680`
- `0x1801184a0`
- `0x180122018`

## import_xrefs

- `ntdll!RtlIsStateSeparationEnabled` at `0x1801184d9`
- `ntdll!RtlIsStateSeparationEnabled` at `0x180118531`
- `ntdll!RtlIsStateSeparationEnabled` at `0x1801184d9`
- `ntdll!RtlIsStateSeparationEnabled` at `0x180118531`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x1801184c8`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x1801184c8`
- `api-ms-win-shcore-stream-l1-1-0!SHCreateMemStream` at `0x180118544`
- `api-ms-win-shcore-stream-l1-1-0!SHCreateMemStream` at `0x180118544`

## string_xrefs

- `0x1801184df`: `<?xml version="1.0" encoding="utf-16"?>\n<DiagData>\n  <DataSource name="WAP">\n    <Key>\n      <Category>Bootstrap</Category>\n      <Path>HKLM\Software\Microsoft\WAP\*</Path>\n      <Representation>Type</Representation>\n      <Value>\n        <Name>*</Name>\n        <ValueRepresentation>*</ValueRepresentation>\n      </Value>\n      <Key>\n        <Category>Proxy</Category>\n        <Path>*</Path>\n        <Representation>Name</Representation>\n        <Value>\n          <Name>*</Name>\n    `
- `0x1801184e6`: `<?xml version="1.0" encoding="utf-16"?>\n<DiagData>\n  <DataSource name="OSDataWAP">\n    <Key>\n      <Category>Bootstrap</Category>\n      <Path>HKLM\OSData\Software\Microsoft\WAP\*</Path>\n      <Representation>Type</Representation>\n      <Value>\n        <Name>*</Name>\n        <ValueRepresentation>*</ValueRepresentation>\n      </Value>\n      <Key>\n        <Category>Proxy</Category>\n        <Path>*</Path>\n        <Representation>Name</Representation>\n        <Value>\n          <Name>*`
- `0x180118523`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\dll\wapdiagdata.cpp`

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
0x1801184a0  mov     rax, rsp
0x1801184a3  mov     [rax+8], rbx
0x1801184a7  mov     [rax+10h], rbp
0x1801184ab  push    rsi
0x1801184ac  push    rdi
0x1801184ad  push    r14; int
0x1801184af  sub     rsp, 20h
0x1801184b3  mov     rsi, rdx
0x1801184b6  xor     ebp, ebp
0x1801184b8  mov     [rax+18h], rbp
0x1801184bc  mov     [rax+20h], rbp
0x1801184c0  mov     r8, rdx; ppstm
0x1801184c3  lea     edx, [rbp+1]; fDeleteOnRelease
0x1801184c6  xor     ecx, ecx; hGlobal
0x1801184c8  call    cs:__imp_CreateStreamOnHGlobal
0x1801184ce  mov     ebx, eax
0x1801184d0  test    eax, eax
0x1801184d2  jns     short loc_1801184D9
0x1801184d4  lea     edx, [rbp+31h]
0x1801184d7  jmp     short loc_18011851B
0x1801184d9  call    cs:__imp_RtlIsStateSeparationEnabled
0x1801184df  lea     r14, aXmlVersion10En_17; "<?xml version=\"1.0\" encoding=\"utf-16"...
0x1801184e6  lea     rdi, aXmlVersion10En_13; "<?xml version=\"1.0\" encoding=\"utf-16"...
0x1801184ed  mov     rdx, rdi
0x1801184f0  test    al, al
0x1801184f2  cmovz   rdx, r14; unsigned __int64
0x1801184f6  or      rcx, 0FFFFFFFFFFFFFFFFh
0x1801184fa  inc     rcx
0x1801184fd  cmp     [rdx+rcx*2], bp
0x180118501  jnz     short loc_1801184FA
0x180118503  inc     rcx; unsigned __int64
0x180118506  lea     r8, [rsp+38h+cbInit]; unsigned __int64 *
0x18011850b  call    ?ULongLongMult@@YAJ_K0PEA_K@Z; ULongLongMult(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x180118510  mov     ebx, eax
0x180118512  test    eax, eax
0x180118514  jns     short loc_180118531
0x180118516  mov     edx, 32h ; '2'; void *
0x18011851b  mov     rcx, [rsp+38h]; this
0x180118520  mov     r9d, eax; char *
0x180118523  lea     r8, aOnecoreuapAdmi_18; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x18011852a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18011852f  jmp     short loc_180118573
0x180118531  call    cs:__imp_RtlIsStateSeparationEnabled
0x180118537  test    al, al
0x180118539  cmovz   rdi, r14
0x18011853d  mov     edx, dword ptr [rsp+38h+cbInit]; cbInit
0x180118541  mov     rcx, rdi; pInit
0x180118544  call    cs:__imp_SHCreateMemStream
0x18011854a  mov     rdx, rax
0x18011854d  lea     rcx, [rsp+38h+arg_10]
0x180118552  call    ??4?$ComPtr@UIStream@@@WRL@Microsoft@@QEAAAEAV012@PEAUIStream@@@Z; Microsoft::WRL::ComPtr<IStream>::operator=(IStream *)
0x180118557  mov     rdx, [rsi]; struct IStream *
0x18011855a  mov     rcx, [rsp+38h+arg_10]; struct IStream *
0x18011855f  call    ?CreateDiagnosticData@@YAJPEAUIStream@@0@Z; CreateDiagnosticData(IStream *,IStream *)
0x180118564  mov     ebx, eax
0x180118566  test    eax, eax
0x180118568  jns     short loc_180118571
0x18011856a  mov     edx, 37h ; '7'
0x18011856f  jmp     short loc_18011851B
0x180118571  mov     ebx, ebp
0x180118573  lea     rcx, [rsp+38h+arg_10]
0x180118578  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x18011857d  mov     eax, ebx
0x18011857f  mov     rbx, [rsp+38h+arg_0]
0x180118584  mov     rbp, [rsp+38h+arg_8]
0x180118589  add     rsp, 20h
0x18011858d  pop     r14
0x18011858f  pop     rdi
0x180118590  pop     rsi
0x180118591  retn
```
