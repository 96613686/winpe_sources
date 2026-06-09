# _dynamic_initializer_for__c_WifiEnabledFormatString__

- ea: `0x1400025f0`
- end: `0x14000261d`
- name: `_dynamic_initializer_for__c_WifiEnabledFormatString__`
- size: `45`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callees

- `0x140003218`
- `0x14000dd20`

## string_xrefs

- `0x1400025fa`: `<SyncML xmlns="SYNCML:SYNCML1.1">  <SyncBody>    <Replace xmlns="">        <CmdID>1</CmdID>        <Item>            <Meta>                <Format>int</Format>                <Type>text/plain</Type>            </Meta>            <Target>                <LocURI>./Vendor/MSFT/Policy/Config/Wifi/AllowWiFi</LocURI>            </Target>            <Data>{}</Data>        </Item>    </Replace>    <Final xmlns="" />  </SyncBody></SyncML>`

## pseudocode

```c
int dynamic_initializer_for__c_WifiEnabledFormatString__()
{
  std::wstring::_Construct<1,unsigned short const *>(
    qword_140075C88,
    L"<SyncML xmlns=\"SYNCML:SYNCML1.1\">  <SyncBody>    <Replace xmlns=\"\">        <CmdID>1</CmdID>        <Item>       "
     "     <Meta>                <Format>int</Format>                <Type>text/plain</Type>            </Meta>          "
     "  <Target>                <LocURI>./Vendor/MSFT/Policy/Config/Wifi/AllowWiFi</LocURI>            </Target>         "
     "   <Data>{}</Data>        </Item>    </Replace>    <Final xmlns=\"\" />  </SyncBody></SyncML>",
    0x1B1u);
  return atexit((void (__cdecl *)())dynamic_atexit_destructor_for__c_WifiEnabledFormatString__);
}

```

## disassembly

```asm
0x1400025f0  sub     rsp, 28h
0x1400025f4  mov     r8d, 1B1h
0x1400025fa  lea     rdx, aSyncmlXmlnsSyn; "<SyncML xmlns=\"SYNCML:SYNCML1.1\">  <S"...
0x140002601  lea     rcx, qword_140075C88
0x140002608  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x14000260d  lea     rcx, _dynamic_atexit_destructor_for__c_WifiEnabledFormatString__
0x140002614  add     rsp, 28h
0x140002618  jmp     atexit
```
