# Windows::Internal::StringReference::StringReference(ushort const (&)[13])

- ea: `0x100a0a66`
- end: `0x100a0a98`
- name: `??$?0$0N@@StringReference@Internal@Windows@@QAE@AAY0N@$$CBG@Z`
- size: `50`
- prototype: `void __thiscall(Windows::Internal::StringReference *this, const wchar_t (*)[13])`
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x100a1d90`
- `0x1013d920`

## callees

- `0x100a0a66`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x100a0a8c`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x100a0a8c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x100a0a77`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x100a0a77`

## string_xrefs

- `0x100a0a72`: `xml_file.xml`

## pseudocode

```c
void __thiscall Windows::Internal::StringReference::StringReference(
        Windows::Internal::StringReference *this,
        const wchar_t (*a2)[13])
{
  if ( WindowsCreateStringReference(L"xml_file.xml", 0xCu, &this->_header, &this->_hstring) < 0 )
    RaiseException(0xC000000D, 1u, 0, 0);
}

```

## disassembly

```asm
0x100a0a66  mov     edi, edi
0x100a0a68  push    esi
0x100a0a69  mov     esi, this
0x100a0a6b  push    esi; string
0x100a0a6c  lea     eax, [esi+4]
0x100a0a6f  push    eax; hstringHeader
0x100a0a70  push    0Ch; length
0x100a0a72  push    offset aXmlFileXml; "xml_file.xml"
0x100a0a77  call    ds:__imp__WindowsCreateStringReference@16; WindowsCreateStringReference(x,x,x,x)
0x100a0a7d  test    eax, eax
0x100a0a7f  jns     short loc_100A0A92
0x100a0a81  push    0; lpArguments
0x100a0a83  push    0; nNumberOfArguments
0x100a0a85  push    1; dwExceptionFlags
0x100a0a87  push    0C000000Dh; dwExceptionCode
0x100a0a8c  call    ds:__imp__RaiseException@16; RaiseException(x,x,x,x)
0x100a0a92  mov     eax, esi
0x100a0a94  pop     esi
0x100a0a95  retn    4
```
