# Windows::Internal::StringReference::StringReference(ushort const (&)[13])

- ea: `0x1800eb568`
- end: `0x1800eb5ac`
- name: `??$?0$0N@@StringReference@Internal@Windows@@QEAA@AEAY0N@$$CBG@Z`
- size: `68`
- prototype: `void __fastcall(Windows::Internal::StringReference *this, const wchar_t (*)[13])`
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x1800ec8f0`
- `0x18015c110`

## callees

- `0x1800eb568`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800eb59d`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800eb59d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800eb584`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800eb584`

## string_xrefs

- `0x1800eb57d`: `xml_file.xml`

## pseudocode

```c
void __fastcall Windows::Internal::StringReference::StringReference(
        Windows::Internal::StringReference *this,
        const wchar_t (*a2)[13])
{
  if ( WindowsCreateStringReference(L"xml_file.xml", 0xCu, &this->_header, &this->_hstring) < 0 )
    RaiseException(0xC000000D, 1u, 0, 0);
}

```

## disassembly

```asm
0x1800eb568  push    rbx
0x1800eb56a  sub     rsp, 20h
0x1800eb56e  mov     rbx, this
0x1800eb571  lea     r8, [this+8]; hstringHeader
0x1800eb575  mov     r9, this; string
0x1800eb578  mov     edx, 0Ch; length
0x1800eb57d  lea     this, aXmlFileXml; "xml_file.xml"
0x1800eb584  call    cs:__imp_WindowsCreateStringReference
0x1800eb58a  test    eax, eax
0x1800eb58c  jns     short loc_1800EB5A3
0x1800eb58e  xor     r9d, r9d; lpArguments
0x1800eb591  xor     r8d, r8d; nNumberOfArguments
0x1800eb594  mov     ecx, 0C000000Dh; dwExceptionCode
0x1800eb599  lea     edx, [r9+1]; dwExceptionFlags
0x1800eb59d  call    cs:__imp_RaiseException
0x1800eb5a3  mov     rax, rbx
0x1800eb5a6  add     rsp, 20h
0x1800eb5aa  pop     rbx
0x1800eb5ab  retn
```
