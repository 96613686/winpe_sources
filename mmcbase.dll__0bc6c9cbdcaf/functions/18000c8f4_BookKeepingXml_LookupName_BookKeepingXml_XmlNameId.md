# BookKeepingXml::LookupName(BookKeepingXml::_XmlNameId)

- ea: `0x18000c8f4`
- end: `0x18000c90b`
- name: `?LookupName@BookKeepingXml@@CAPEBGW4_XmlNameId@1@@Z`
- size: `23`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x18000c2d8`
- `0x18000c60c`
- `0x18000c64c`

## callees

- `0x18000c8f4`

## pseudocode

```c
const unsigned __int16 * near *__fastcall BookKeepingXml::LookupName(unsigned int a1)
{
  if ( a1 > 0x31 )
    return 0;
  else
    return (&BookKeepingXml::s_ppszXmlNames)[a1];
}

```

## disassembly

```asm
0x18000c8f4  cmp     ecx, 31h ; '1'
0x18000c8f7  ja      short loc_18000C908
0x18000c8f9  movsxd  rax, ecx
0x18000c8fc  lea     rcx, ?s_ppszXmlNames@BookKeepingXml@@0PAPEBGA; ushort const * near * BookKeepingXml::s_ppszXmlNames
0x18000c903  mov     rax, [rcx+rax*8]
0x18000c907  retn
0x18000c908  xor     eax, eax
0x18000c90a  retn
```
