# _dynamic_initializer_for__c_WifiEnabledFormatString___0

- ea: `0x140002900`
- end: `0x14000292d`
- name: `_dynamic_initializer_for__c_WifiEnabledFormatString___0`
- size: `45`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callees

- `0x140003218`
- `0x14000dd20`

## string_xrefs

- `0x14000290a`: `<SyncML xmlns="SYNCML:SYNCML1.1">  <SyncBody>    <Replace xmlns="">        <CmdID>1</CmdID>        <Item>            <Meta>                <Format>int</Format>                <Type>text/plain</Type>            </Meta>            <Target>                <LocURI>./Vendor/MSFT/Policy/Config/Wifi/AllowWiFi</LocURI>            </Target>            <Data>{}</Data>        </Item>    </Replace>    <Final xmlns="" />  </SyncBody></SyncML>`

## pseudocode

```c
int dynamic_initializer_for__c_WifiEnabledFormatString___0()
{
  std::wstring::_Construct<1,unsigned short const *>(
    &qword_140075CA8,
    L"<SyncML xmlns=\"SYNCML:SYNCML1.1\">  <SyncBody>    <Replace xmlns=\"\">        <CmdID>1</CmdID>        <Item>       "
     "     <Meta>                <Format>int</Format>                <Type>text/plain</Type>            </Meta>          "
     "  <Target>                <LocURI>./Vendor/MSFT/Policy/Config/Wifi/AllowWiFi</LocURI>            </Target>         "
     "   <Data>{}</Data>        </Item>    </Replace>    <Final xmlns=\"\" />  </SyncBody></SyncML>",
    0x1B1u);
  return atexit((void (__cdecl *)())dynamic_atexit_destructor_for__c_WifiEnabledFormatString___0);
}

```

## disassembly

```asm
0x140002900  sub     rsp, 28h
0x140002904  mov     r8d, 1B1h
0x14000290a  lea     rdx, aSyncmlXmlnsSyn; "<SyncML xmlns=\"SYNCML:SYNCML1.1\">  <S"...
0x140002911  lea     rcx, qword_140075CA8
0x140002918  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x14000291d  lea     rcx, _dynamic_atexit_destructor_for__c_WifiEnabledFormatString___0
0x140002924  add     rsp, 28h
0x140002928  jmp     atexit
```
