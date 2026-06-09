# GetTemplate

- ea: `0x180117420`
- end: `0x18011746d`
- name: `GetTemplate`
- size: `77`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x1801172e0`

## callees

- `0x180117420`

## import_xrefs

- `ntdll!RtlIsStateSeparationEnabled` at `0x180117428`
- `ntdll!RtlIsStateSeparationEnabled` at `0x180117444`
- `ntdll!RtlIsStateSeparationEnabled` at `0x180117428`
- `ntdll!RtlIsStateSeparationEnabled` at `0x180117444`

## string_xrefs

- `0x180117450`: `<?xml version="1.0" encoding="utf-16"?>\n<DiagData>\n  <DataSource name="PolicyManager">\n    <Key>\n      <Category>ConfigSource</Category>\n      <Path>HKLM\Software\Microsoft\PolicyManager\providers\*</Path>\n      <Representation>EnrollmentId</Representation>\n      <Key>\n        <Category>PolicyScope</Category>\n        <Path>default\*</Path>\n        <Representation>PolicyScope</Representation>\n        <Key>\n          <Category>Area</Category>\n          <Path>*</Path>\n          <Repre`
- `0x180117434`: `<?xml version="1.0" encoding="utf-16"?>\n<DiagData>\n  <DataSource name="PolicyManagerMeta">\n    <Key>\n      <Category>AreaMetadata</Category>\n      <Path>HKLM\Software\Microsoft\PolicyManager\default\*</Path>\n      <Representation>PolicyAreaName</Representation>\n      <Key>\n        <Category>PolicyMetadata</Category>\n        <Path>*</Path>\n        <Representation>PolicyName</Representation>\n        <Value>\n          <Name>*</Name>\n          <ValueRepresentation>*</ValueRepresentation`
- `0x180117457`: `<?xml version="1.0" encoding="utf-16"?>\n<DiagData>\n  <DataSource name="OSDataPolicyManager">\n    <Key>\n      <Category>ConfigSource</Category>\n      <Path>HKLM\OSData\Software\Microsoft\PolicyManager\providers\*</Path>\n      <Representation>EnrollmentId</Representation>\n      <Key>\n        <Category>PolicyScope</Category>\n        <Path>default\*</Path>\n        <Representation>PolicyScope</Representation>\n        <Key>\n          <Category>Area</Category>\n          <Path>*</Path>\n   `
- `0x18011743b`: `<?xml version="1.0" encoding="utf-16"?>\n<DiagData>\n  <DataSource name="OSDataPolicyManagerMeta">\n    <Key>\n      <Category>AreaMetadata</Category>\n      <Path>HKLM\OSData\Software\Microsoft\PolicyManager\default\*</Path>\n      <Representation>PolicyAreaName</Representation>\n      <Key>\n        <Category>PolicyMetadata</Category>\n        <Path>*</Path>\n        <Representation>PolicyName</Representation>\n        <Value>\n          <Name>*</Name>\n          <ValueRepresentation>*</ValueR`

## pseudocode

```c
const wchar_t *__fastcall GetTemplate(char a1)
{
  char IsStateSeparationEnabled; // al
  const wchar_t *v2; // rdx
  const wchar_t *v3; // rcx

  if ( a1 )
  {
    IsStateSeparationEnabled = RtlIsStateSeparationEnabled();
    v2 = L"<?xml version=\"1.0\" encoding=\"utf-16\"?>\n"
          "<DiagData>\n"
          "  <DataSource name=\"PolicyManagerMeta\">\n"
          "    <Key>\n"
          "      <Category>AreaMetadata</Category>\n"
          "      <Path>HKLM\\Software\\Microsoft\\PolicyManager\\default\\*</Path>\n"
          "      <Representation>PolicyAreaName</Representation>\n"
          "      <Key>\n"
          "        <Category>PolicyMetadata</Category>\n"
          "        <Path>*</Path>\n"
          "        <Representation>PolicyName</Representation>\n"
          "        <Value>\n"
          "          <Name>*</Name>\n"
          "          <ValueRepresentation>*</ValueRepresentation>\n"
          "        </Value>\n"
          "      </Key>\n"
          "    </Key>\n"
          "  </DataSource>\n"
          "</DiagData>";
    v3 = L"<?xml version=\"1.0\" encoding=\"utf-16\"?>\n"
          "<DiagData>\n"
          "  <DataSource name=\"OSDataPolicyManagerMeta\">\n"
          "    <Key>\n"
          "      <Category>AreaMetadata</Category>\n"
          "      <Path>HKLM\\OSData\\Software\\Microsoft\\PolicyManager\\default\\*</Path>\n"
          "      <Representation>PolicyAreaName</Representation>\n"
          "      <Key>\n"
          "        <Category>PolicyMetadata</Category>\n"
          "        <Path>*</Path>\n"
          "        <Representation>PolicyName</Representation>\n"
          "        <Value>\n"
          "          <Name>*</Name>\n"
          "          <ValueRepresentation>*</ValueRepresentation>\n"
          "        </Value>\n"
          "      </Key>\n"
          "    </Key>\n"
          "  </DataSource>\n"
          "</DiagData>";
  }
  else
  {
    IsStateSeparationEnabled = RtlIsStateSeparationEnabled();
    v2 = L"<?xml version=\"1.0\" encoding=\"utf-16\"?>\n"
          "<DiagData>\n"
          "  <DataSource name=\"PolicyManager\">\n"
          "    <Key>\n"
          "      <Category>ConfigSource</Category>\n"
          "      <Path>HKLM\\Software\\Microsoft\\PolicyManager\\providers\\*</Path>\n"
          "      <Representation>EnrollmentId</Representation>\n"
          "      <Key>\n"
          "        <Category>PolicyScope</Category>\n"
          "        <Path>default\\*</Path>\n"
          "        <Representation>PolicyScope</Representation>\n"
          "        <Key>\n"
          "          <Category>Area</Category>\n"
          "          <Path>*</Path>\n"
          "          <Representation>PolicyAreaName</Representation>\n"
          "          <Value>\n"
          "            <Name>*</Name>\n"
          "            <ValueRepresentation>*</ValueRepresentation>\n"
          "          </Value>\n"
          "        </Key>\n"
          "      </Key>\n"
          "    </Key>\n"
          "    <Key>\n"
          "      <Category>CurrentPolicies</Category>\n"
          "      <Path>HKLM\\Software\\Microsoft\\PolicyManager\\current\\*</Path>\n"
          "      <Representation>PolicyScope</Representation>\n"
          "      <Key>\n"
          "        <Category>CurrentPolicyValues</Category>\n"
          "        <Path>*</Path>\n"
          "        <Representation>PolicyAreaName</Representation>\n"
          "        <Value>\n"
          "          <Name>*</Name>\n"
          "          <ValueRepresentation>*</ValueRepresentation>\n"
          "        </Value>\n"
          "      </Key>\n"
          "    </Key>\n"
          "    <Key>\n"
          "      <Category>EASPolicy</Category>\n"
          "      <Path>HKLM\\Software\\Microsoft\\PolicyManager\\EASCache\\*</Path>\n"
          "      <Representation>EnrollmentId</Representation>\n"
          "      <Key>\n"
          "        <Category>PolicyCategory</Category>\n"
          "        <Path>*</Path>\n"
          "        <Representation>Importance</Representation>\n"
          "        <Value>\n"
          "          <Name>*</Name>\n"
          "          <ValueRepresentation>*</ValueRepresentation>\n"
          "        </Value>\n"
          "      </Key>\n"
          "    </Key>\n"
          "    <Key>\n"
          "      <Category>IngestedADMXPolicyMetaData</Category>\n"
          "      <Path>HKLM\\Software\\Microsoft\\PolicyManager\\ADMXDefault\\*</Path>\n"
          "      <Representation>EnrollmentId</Representation>\n"
          "      <Key>\n"
          "        <Category>AreaName</Category>\n"
          "        <Path>*</Path>\n"
          "        <Representation>ADMXIngestedAreaName</Representation>\n"
          "        <Key>\n"
          "          <Category>PolicyMetadata</Category>\n"
          "          <Path>*</Path>\n"
          "          <Representation>PolicyName</Representation>\n"
          "          <Value>\n"
          "            <Name>*</Name>\n"
          "            <ValueRepresentation>*</ValueRepresentation>\n"
          "          </Value>\n"
          "        </Key>\n"
          "      </Key>\n"
          "    </Key>\n"
          "    <Key>\n"
          "      <Category>IngestedADMXInstallData</Category>\n"
          "      <Path>HKLM\\Software\\Microsoft\\PolicyManager\\AdmxInstalled\\*</Path>\n"
          "      <Representation>EnrollmentId</Representation>\n"
          "      <Key>\n"
          "        <Category>ADMXIngestedAppName</Category>\n"
          "        <Path>*</Path>\n"
          "        <Representation>AppName</Representation>\n"
          "        <Key>\n"
          "            <Category>ADMXIngestedSettingType</Category>\n"
          "            <Path>*</Path>\n"
          "            <Representation>SettingType</Representation>\n"
          "            <Key>\n"
          "              <Category>ADMXIngestedFileID</Category>\n"
          "              <Path>*</Path>\n"
          "              <Representation>FileUID</Representation>\n"
          "              <Value>\n"
          "                <Name>*</Name>\n"
          "                <ValueRepresentation>*</ValueRepresentation>\n"
          "              </Value>\n"
          "            </Key>\n"
          "        </Key>\n"
          "      </Key>\n"
          "    </Key>\n"
          "  </DataSource>\n"
          "</DiagData>";
    v3 = L"<?xml version=\"1.0\" encoding=\"utf-16\"?>\n"
          "<DiagData>\n"
          "  <DataSource name=\"OSDataPolicyManager\">\n"
          "    <Key>\n"
          "      <Category>ConfigSource</Category>\n"
          "      <Path>HKLM\\OSData\\Software\\Microsoft\\PolicyManager\\providers\\*</Path>\n"
          "      <Representation>EnrollmentId</Representation>\n"
          "      <Key>\n"
          "        <Category>PolicyScope</Category>\n"
          "        <Path>default\\*</Path>\n"
          "        <Representation>PolicyScope</Representation>\n"
          "        <Key>\n"
          "          <Category>Area</Category>\n"
          "          <Path>*</Path>\n"
          "          <Representation>PolicyAreaName</Representation>\n"
          "          <Value>\n"
          "            <Name>*</Name>\n"
          "            <ValueRepresentation>*</ValueRepresentation>\n"
          "          </Value>\n"
          "        </Key>\n"
          "      </Key>\n"
          "    </Key>\n"
          "    <Key>\n"
          "      <Category>CurrentPolicies</Category>\n"
          "      <Path>HKLM\\OSData\\Software\\Microsoft\\PolicyManager\\current\\*</Path>\n"
          "      <Representation>PolicyScope</Representation>\n"
          "      <Key>\n"
          "        <Category>CurrentPolicyValues</Category>\n"
          "        <Path>*</Path>\n"
          "        <Representation>PolicyAreaName</Representation>\n"
          "        <Value>\n"
          "          <Name>*</Name>\n"
          "          <ValueRepresentation>*</ValueRepresentation>\n"
          "        </Value>\n"
          "      </Key>\n"
          "    </Key>\n"
          "    <Key>\n"
          "      <Category>EASPolicy</Category>\n"
          "      <Path>HKLM\\OSData\\Software\\Microsoft\\PolicyManager\\EASCache\\*</Path>\n"
          "      <Representation>EnrollmentId</Representation>\n"
          "      <Key>\n"
          "        <Category>PolicyCategory</Category>\n"
          "        <Path>*</Path>\n"
          "        <Representation>Importance</Representation>\n"
          "        <Value>\n"
          "          <Name>*</Name>\n"
          "          <ValueRepresentation>*</ValueRepresentation>\n"
          "        </Value>\n"
          "      </Key>\n"
          "    </Key>\n"
          "    <Key>\n"
          "      <Category>IngestedADMXPolicyMetaData</Category>\n"
          "      <Path>HKLM\\OSData\\Software\\Microsoft\\PolicyManager\\ADMXDefault\\*</Path>\n"
          "      <Representation>EnrollmentId</Representation>\n"
          "      <Key>\n"
          "        <Category>AreaName</Category>\n"
          "        <Path>*</Path>\n"
          "        <Representation>ADMXIngestedAreaName</Representation>\n"
          "        <Key>\n"
          "          <Category>PolicyMetadata</Category>\n"
          "          <Path>*</Path>\n"
          "          <Representation>PolicyName</Representation>\n"
          "          <Value>\n"
          "            <Name>*</Name>\n"
          "            <ValueRepresentation>*</ValueRepresentation>\n"
          "          </Value>\n"
          "        </Key>\n"
          "      </Key>\n"
          "    </Key>\n"
          "    <Key>\n"
          "      <Category>IngestedADMXInstallData</Category>\n"
          "      <Path>HKLM\\OSData\\Software\\Microsoft\\PolicyManager\\AdmxInstalled\\*</Path>\n"
          "      <Representation>EnrollmentId</Representation>\n"
          "      <Key>\n"
          "        <Category>ADMXIngestedAppName</Category>\n"
          "        <Path>*</Path>\n"
          "        <Representation>AppName</Representation>\n"
          "        <Key>\n"
          "            <Category>ADMXIngestedSettingType</Category>\n"
          "            <Path>*</Path>\n"
          "            <Representation>SettingType</Representation>\n"
          "            <Key>\n"
          "              <Category>ADMXIngestedFileID</Category>\n"
          "              <Path>*</Path>\n"
          "              <Representation>FileUID</Representation>\n"
          "              <Value>\n"
          "                <Name>*</Name>\n"
          "                <ValueRepresentation>*</ValueRepresentation>\n"
          "              </Value>\n"
          "            </Key>\n"
          "        </Key>\n"
          "      </Key>\n"
          "    </Key>\n"
          "  </DataSource>\n"
          "</DiagData>";
  }
  if ( !IsStateSeparationEnabled )
    return v2;
  return v3;
}

```

## disassembly

```asm
0x180117420  sub     rsp, 28h
0x180117424  test    cl, cl
0x180117426  jz      short loc_180117444
0x180117428  call    cs:__imp_RtlIsStateSeparationEnabled
0x18011742f  nop     dword ptr [rax+rax+00h]
0x180117434  lea     rdx, aXmlVersion10En_1; "<?xml version=\"1.0\" encoding=\"utf-16"...
0x18011743b  lea     rcx, aXmlVersion10En_18; "<?xml version=\"1.0\" encoding=\"utf-16"...
0x180117442  jmp     short loc_18011745E
0x180117444  call    cs:__imp_RtlIsStateSeparationEnabled
0x18011744b  nop     dword ptr [rax+rax+00h]
0x180117450  lea     rdx, aXmlVersion10En_15; "<?xml version=\"1.0\" encoding=\"utf-16"...
0x180117457  lea     rcx, aXmlVersion10En_10; "<?xml version=\"1.0\" encoding=\"utf-16"...
0x18011745e  test    al, al
0x180117460  cmovz   rcx, rdx
0x180117464  mov     rax, rcx
0x180117467  add     rsp, 28h
0x18011746b  retn
```
