# OSKDuiFrame::CreateStyleParser(DirectUI::DUIXmlParser * *)

- ea: `0x14000ed60`
- end: `0x14000ede9`
- name: `?CreateStyleParser@OSKDuiFrame@@EEAAJPEAPEAVDUIXmlParser@DirectUI@@@Z`
- size: `137`
- prototype: `__int64 __fastcall(OSKDuiFrame *__hidden this, struct DirectUI::DUIXmlParser **)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x14000ed60`

## import_xrefs

- `DUI70!?Create@DUIXmlParser@DirectUI@@SAJPEAPEAV12@P6APEAVValue@2@PEBGPEAX@Z2P6AX11H2@Z2@Z` at `0x14000ed92`
- `DUI70!?Create@DUIXmlParser@DirectUI@@SAJPEAPEAV12@P6APEAVValue@2@PEBGPEAX@Z2P6AX11H2@Z2@Z` at `0x14000ed92`
- `DUI70!?Destroy@DUIXmlParser@DirectUI@@QEAAXXZ` at `0x14000edd1`
- `DUI70!?Destroy@DUIXmlParser@DirectUI@@QEAAXXZ` at `0x14000edd1`
- `DUI70!?SetXMLFromResource@DUIXmlParser@DirectUI@@QEAAJIPEAUHINSTANCE__@@0@Z` at `0x14000edb6`
- `DUI70!?SetXMLFromResource@DUIXmlParser@DirectUI@@QEAAJIPEAUHINSTANCE__@@0@Z` at `0x14000edb6`

## pseudocode

```c
__int64 __fastcall OSKDuiFrame::CreateStyleParser(HINSTANCE *this, struct DirectUI::DUIXmlParser **a2)
{
  int v4; // ebx
  struct DirectUI::DUIXmlParser *v6; // [rsp+50h] [rbp+18h] BYREF

  v6 = 0;
  v4 = DirectUI::DUIXmlParser::Create(&v6, 0, 0, 0, 0);
  if ( v4 >= 0 )
  {
    v4 = DirectUI::DUIXmlParser::SetXMLFromResource(v6, 0xC8u, this[33], &_ImageBase);
    if ( v4 < 0 )
      DirectUI::DUIXmlParser::Destroy(v6);
    else
      *a2 = v6;
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x14000ed60  mov     rax, rsp
0x14000ed63  mov     [rax+8], rbx
0x14000ed67  mov     [rax+10h], rsi
0x14000ed6b  push    rdi
0x14000ed6c  sub     rsp, 30h
0x14000ed70  mov     rdi, rdx
0x14000ed73  mov     qword ptr [rax+18h], 0
0x14000ed7b  mov     rsi, rcx
0x14000ed7e  mov     qword ptr [rax-18h], 0
0x14000ed86  xor     edx, edx
0x14000ed88  lea     rcx, [rax+18h]
0x14000ed8c  xor     r9d, r9d
0x14000ed8f  xor     r8d, r8d
0x14000ed92  call    cs:__imp_?Create@DUIXmlParser@DirectUI@@SAJPEAPEAV12@P6APEAVValue@2@PEBGPEAX@Z2P6AX11H2@Z2@Z; DirectUI::DUIXmlParser::Create(DirectUI::DUIXmlParser * *,DirectUI::Value * (*)(ushort const *,void *),void *,void (*)(ushort const *,ushort const *,int,void *),void *)
0x14000ed98  mov     ebx, eax
0x14000ed9a  test    eax, eax
0x14000ed9c  js      short loc_14000EDD7
0x14000ed9e  mov     r8, [rsi+108h]
0x14000eda5  lea     r9, __ImageBase
0x14000edac  mov     rcx, [rsp+38h+arg_10]
0x14000edb1  mov     edx, 0C8h
0x14000edb6  call    cs:__imp_?SetXMLFromResource@DUIXmlParser@DirectUI@@QEAAJIPEAUHINSTANCE__@@0@Z; DirectUI::DUIXmlParser::SetXMLFromResource(uint,HINSTANCE__ *,HINSTANCE__ *)
0x14000edbc  mov     ebx, eax
0x14000edbe  test    eax, eax
0x14000edc0  js      short loc_14000EDCC
0x14000edc2  mov     rax, [rsp+38h+arg_10]
0x14000edc7  mov     [rdi], rax
0x14000edca  jmp     short loc_14000EDD7
0x14000edcc  mov     rcx, [rsp+38h+arg_10]
0x14000edd1  call    cs:__imp_?Destroy@DUIXmlParser@DirectUI@@QEAAXXZ; DirectUI::DUIXmlParser::Destroy(void)
0x14000edd7  mov     rsi, [rsp+38h+arg_8]
0x14000eddc  mov     eax, ebx
0x14000edde  mov     rbx, [rsp+38h+arg_0]
0x14000ede3  add     rsp, 30h
0x14000ede7  pop     rdi
0x14000ede8  retn
```
