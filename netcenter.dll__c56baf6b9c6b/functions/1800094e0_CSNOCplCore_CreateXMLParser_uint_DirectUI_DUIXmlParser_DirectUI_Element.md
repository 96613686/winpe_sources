# CSNOCplCore::CreateXMLParser(uint,DirectUI::DUIXmlParser * *,DirectUI::Element * *)

- ea: `0x1800094e0`
- end: `0x1800095b8`
- name: `?CreateXMLParser@CSNOCplCore@@AEAAJIPEAPEAVDUIXmlParser@DirectUI@@PEAPEAVElement@3@@Z`
- size: `216`
- prototype: `__int64 __fastcall(CSNOCplCore *__hidden this, unsigned int, struct DirectUI::DUIXmlParser **, struct DirectUI::Element **)`
- caller_count: `3`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x180008b7c`
- `0x18000c36c`
- `0x18000c5b4`

## callees

- `0x1800094e0`

## import_xrefs

- `DUI70!?CreateElement@DUIXmlParser@DirectUI@@QEAAJPEBGPEAVElement@2@1PEAKPEAPEAV32@@Z` at `0x18000958a`
- `DUI70!?CreateElement@DUIXmlParser@DirectUI@@QEAAJPEBGPEAVElement@2@1PEAKPEAPEAV32@@Z` at `0x18000958a`
- `DUI70!?SetXMLFromResource@DUIXmlParser@DirectUI@@QEAAJIPEAUHINSTANCE__@@0@Z` at `0x180009550`
- `DUI70!?SetXMLFromResource@DUIXmlParser@DirectUI@@QEAAJIPEAUHINSTANCE__@@0@Z` at `0x180009550`
- `DUI70!?Create@DUIXmlParser@DirectUI@@SAJPEAPEAV12@P6APEAVValue@2@PEBGPEAX@Z2P6AX11H2@Z2@Z` at `0x18000952f`
- `DUI70!?Create@DUIXmlParser@DirectUI@@SAJPEAPEAV12@P6APEAVValue@2@PEBGPEAX@Z2P6AX11H2@Z2@Z` at `0x18000952f`

## pseudocode

```c
__int64 __fastcall CSNOCplCore::CreateXMLParser(
        CSNOCplCore *this,
        unsigned int a2,
        struct DirectUI::DUIXmlParser **a3,
        struct DirectUI::Element **a4)
{
  int v7; // ecx
  struct DirectUI::DUIXmlParser *v9; // [rsp+40h] [rbp+8h] BYREF
  struct DirectUI::Element *v10; // [rsp+50h] [rbp+18h] BYREF

  *a3 = 0;
  *a4 = 0;
  v9 = 0;
  v7 = DirectUI::DUIXmlParser::Create(
         &v9,
         (struct DirectUI::Value *(*)(const unsigned __int16 *, void *))DUIGetSheetCB,
         0,
         (void (*)(const unsigned __int16 *, const unsigned __int16 *, int, void *))DUIParserErrorCB,
         0);
  if ( !v7 )
  {
    v7 = DirectUI::DUIXmlParser::SetXMLFromResource(v9, a2, g_hinst, (HINSTANCE)&_ImageBase);
    if ( v7 >= 0 )
    {
      v10 = 0;
      v7 = DirectUI::DUIXmlParser::CreateElement(v9, L"main", 0, 0, 0, &v10);
      if ( v7 >= 0 )
      {
        *a3 = v9;
        *a4 = v10;
      }
    }
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x1800094e0  mov     rax, rsp
0x1800094e3  mov     [rax+10h], rbx
0x1800094e7  mov     [rax+20h], rsi
0x1800094eb  mov     [rax+8], rcx
0x1800094ef  push    rdi
0x1800094f0  sub     rsp, 30h
0x1800094f4  mov     rbx, r9
0x1800094f7  mov     qword ptr [r8], 0
0x1800094fe  mov     rdi, r8
0x180009501  mov     qword ptr [r9], 0
0x180009508  mov     esi, edx
0x18000950a  mov     qword ptr [rax+8], 0
0x180009512  lea     r9, ?DUIParserErrorCB@@YAXPEBG0HPEAX@Z; DUIParserErrorCB(ushort const *,ushort const *,int,void *)
0x180009519  mov     qword ptr [rax-18h], 0
0x180009521  xor     r8d, r8d
0x180009524  lea     rdx, ?DUIGetSheetCB@@YAPEAVValue@DirectUI@@PEBGPEAX@Z; DUIGetSheetCB(ushort const *,void *)
0x18000952b  lea     rcx, [rax+8]
0x18000952f  call    cs:__imp_?Create@DUIXmlParser@DirectUI@@SAJPEAPEAV12@P6APEAVValue@2@PEBGPEAX@Z2P6AX11H2@Z2@Z; DirectUI::DUIXmlParser::Create(DirectUI::DUIXmlParser * *,DirectUI::Value * (*)(ushort const *,void *),void *,void (*)(ushort const *,ushort const *,int,void *),void *)
0x180009535  mov     ecx, eax
0x180009537  test    eax, eax
0x180009539  jnz     short loc_1800095A6
0x18000953b  mov     r8, cs:g_hinst
0x180009542  lea     r9, __ImageBase
0x180009549  mov     rcx, [rsp+38h+arg_0]
0x18000954e  mov     edx, esi
0x180009550  call    cs:__imp_?SetXMLFromResource@DUIXmlParser@DirectUI@@QEAAJIPEAUHINSTANCE__@@0@Z; DirectUI::DUIXmlParser::SetXMLFromResource(uint,HINSTANCE__ *,HINSTANCE__ *)
0x180009556  mov     ecx, eax
0x180009558  test    eax, eax
0x18000955a  js      short loc_1800095A6
0x18000955c  mov     rcx, [rsp+38h+arg_0]
0x180009561  lea     rax, [rsp+38h+arg_10]
0x180009566  mov     [rsp+38h+var_10], rax
0x18000956b  lea     rdx, aMain; "main"
0x180009572  xor     r9d, r9d
0x180009575  mov     [rsp+38h+var_18], 0
0x18000957e  xor     r8d, r8d
0x180009581  mov     [rsp+38h+arg_10], 0
0x18000958a  call    cs:__imp_?CreateElement@DUIXmlParser@DirectUI@@QEAAJPEBGPEAVElement@2@1PEAKPEAPEAV32@@Z; DirectUI::DUIXmlParser::CreateElement(ushort const *,DirectUI::Element *,DirectUI::Element *,ulong *,DirectUI::Element * *)
0x180009590  mov     ecx, eax
0x180009592  test    eax, eax
0x180009594  js      short loc_1800095A6
0x180009596  mov     rax, [rsp+38h+arg_0]
0x18000959b  mov     [rdi], rax
0x18000959e  mov     rax, [rsp+38h+arg_10]
0x1800095a3  mov     [rbx], rax
0x1800095a6  mov     rbx, [rsp+38h+arg_8]
0x1800095ab  mov     eax, ecx
0x1800095ad  mov     rsi, [rsp+38h+arg_18]
0x1800095b2  add     rsp, 30h
0x1800095b6  pop     rdi
0x1800095b7  retn
```
