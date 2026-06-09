# Windows::Internal::StringReference::StringReference(ushort const (&)[13])

- ea: `0x100a09a6`
- end: `0x100a09d8`
- name: `??$?0$0N@@StringReference@Internal@Windows@@QAE@AAY0N@$$CBG@Z`
- size: `50`
- prototype: `void __thiscall(Windows::Internal::StringReference *this, const wchar_t (*)[13])`
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x100a1ca0`
- `0x1013d810`

## callees

- `0x100a09a6`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x100a09cc`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x100a09cc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x100a09b7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x100a09b7`

## string_xrefs

- `0x100a09b2`: `xml_file.xml`

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
0x100a09a6  mov     edi, edi
0x100a09a8  push    esi
0x100a09a9  mov     esi, this
0x100a09ab  push    esi; string
0x100a09ac  lea     eax, [esi+4]
0x100a09af  push    eax; hstringHeader
0x100a09b0  push    0Ch; length
0x100a09b2  push    offset aXmlFileXml; "xml_file.xml"
0x100a09b7  call    ds:__imp__WindowsCreateStringReference@16; WindowsCreateStringReference(x,x,x,x)
0x100a09bd  test    eax, eax
0x100a09bf  jns     short loc_100A09D2
0x100a09c1  push    0; lpArguments
0x100a09c3  push    0; nNumberOfArguments
0x100a09c5  push    1; dwExceptionFlags
0x100a09c7  push    0C000000Dh; dwExceptionCode
0x100a09cc  call    ds:__imp__RaiseException@16; RaiseException(x,x,x,x)
0x100a09d2  mov     eax, esi
0x100a09d4  pop     esi
0x100a09d5  retn    4
```
