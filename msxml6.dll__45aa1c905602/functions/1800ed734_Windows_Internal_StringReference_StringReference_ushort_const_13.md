# Windows::Internal::StringReference::StringReference(ushort const (&)[13])

- ea: `0x1800ed734`
- end: `0x1800ed785`
- name: `??$?0$0N@@StringReference@Internal@Windows@@QEAA@AEAY0N@$$CBG@Z`
- size: `81`
- prototype: `void __fastcall(Windows::Internal::StringReference *this, const wchar_t (*)[13])`
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x1800eeb70`
- `0x18015f960`

## callees

- `0x1800ed734`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800ed76f`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800ed76f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800ed750`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800ed750`

## string_xrefs

- `0x1800ed749`: `xml_file.xml`

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
0x1800ed734  push    rbx
0x1800ed736  sub     rsp, 20h
0x1800ed73a  mov     rbx, this
0x1800ed73d  lea     r8, [this+8]; hstringHeader
0x1800ed741  mov     r9, this; string
0x1800ed744  mov     edx, 0Ch; length
0x1800ed749  lea     this, aXmlFileXml; "xml_file.xml"
0x1800ed750  call    cs:__imp_WindowsCreateStringReference
0x1800ed757  nop     dword ptr [rax+rax+00h]
0x1800ed75c  test    eax, eax
0x1800ed75e  jns     short loc_1800ED77B
0x1800ed760  xor     r9d, r9d; lpArguments
0x1800ed763  xor     r8d, r8d; nNumberOfArguments
0x1800ed766  mov     ecx, 0C000000Dh; dwExceptionCode
0x1800ed76b  lea     edx, [r9+1]; dwExceptionFlags
0x1800ed76f  call    cs:__imp_RaiseException
0x1800ed776  nop     dword ptr [rax+rax+00h]
0x1800ed77b  mov     rax, rbx
0x1800ed77e  add     rsp, 20h
0x1800ed782  pop     rbx
0x1800ed783  retn
```
