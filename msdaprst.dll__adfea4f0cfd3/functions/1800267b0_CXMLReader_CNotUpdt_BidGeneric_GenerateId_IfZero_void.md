# CXMLReader::CNotUpdt_BidGeneric::GenerateId_IfZero(void)

- ea: `0x1800267b0`
- end: `0x1800267c3`
- name: `?GenerateId_IfZero@CNotUpdt_BidGeneric@CXMLReader@@EEBAXXZ`
- size: `19`
- prototype: `void __fastcall(CXMLReader::CNotUpdt_BidGeneric *__hidden this)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x18001af04`

## string_xrefs

- `0x1800267b3`: `<CXMLReader::CNotUpdt_BidGeneric::GenerateId_IfZero|ID|OBJ|PERSIST> %p{.}`

## pseudocode

```c
void __fastcall CXMLReader::CNotUpdt_BidGeneric::GenerateId_IfZero(CXMLReader::CNotUpdt_BidGeneric *this)
{
  bidObtainItemIdIfZeroW(
    (char *)this + 8,
    L"<CXMLReader::CNotUpdt_BidGeneric::GenerateId_IfZero|ID|OBJ|PERSIST> %p{.}",
    this);
}

```

## disassembly

```asm
0x1800267b0  mov     r8, rcx
0x1800267b3  lea     rdx, aCxmlreaderCnot_0; "<CXMLReader::CNotUpdt_BidGeneric::Gener"...
0x1800267ba  add     rcx, 8
0x1800267be  jmp     _bidObtainItemIdIfZeroW
```
