# DuiTaskDlg::_GetDuiString(int)

- ea: `0x1800026c8`
- end: `0x1800027c3`
- name: `?_GetDuiString@DuiTaskDlg@@IEAAPEBGH@Z`
- size: `251`
- prototype: `const unsigned __int16 *__fastcall(DuiTaskDlg *__hidden this, int)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, service_task`

## callers

- `0x180002f00`

## callees

- `0x1800026c8`

## import_xrefs

- `DUI70!?Create@DUIXmlParser@DirectUI@@SAJPEAPEAV12@P6APEAVValue@2@PEBGPEAX@Z2P6AX11H2@Z2@Z` at `0x180002740`
- `DUI70!?Create@DUIXmlParser@DirectUI@@SAJPEAPEAV12@P6APEAVValue@2@PEBGPEAX@Z2P6AX11H2@Z2@Z` at `0x180002740`
- `DUI70!?SetXMLFromResource@DUIXmlParser@DirectUI@@QEAAJIPEAUHINSTANCE__@@0@Z` at `0x18000275c`
- `DUI70!?SetXMLFromResource@DUIXmlParser@DirectUI@@QEAAJIPEAUHINSTANCE__@@0@Z` at `0x18000275c`
- `DUI70!?CreateElement@DUIXmlParser@DirectUI@@QEAAJPEBGPEAVElement@2@1PEAKPEAPEAV32@@Z` at `0x180002785`
- `DUI70!?CreateElement@DUIXmlParser@DirectUI@@QEAAJPEBGPEAVElement@2@1PEAKPEAPEAV32@@Z` at `0x180002785`
- `DUI70!InitThread` at `0x18000270f`
- `DUI70!InitThread` at `0x18000270f`
- `DUI70!CreateDUIWrapper` at `0x1800027a4`
- `DUI70!CreateDUIWrapper` at `0x1800027a4`
- `DUI70!?EndDefer@Element@DirectUI@@QEAAXK@Z` at `0x180002796`
- `DUI70!?EndDefer@Element@DirectUI@@QEAAXK@Z` at `0x180002796`

## pseudocode

```c
const unsigned __int16 *__fastcall DuiTaskDlg::_GetDuiString(DuiTaskDlg *this, unsigned int a2)
{
  HINSTANCE *v2; // rdi
  struct DirectUI::Element **v3; // rbx
  DirectUI::DUIXmlParser **v4; // rsi
  __int64 v6; // [rsp+40h] [rbp+8h] BYREF
  unsigned int v7; // [rsp+48h] [rbp+10h] BYREF

  v7 = a2;
  v2 = (HINSTANCE *)*((_QWORD *)this + 3);
  v3 = (struct DirectUI::Element **)((char *)this + 192);
  v6 = 0;
  v7 = 0;
  *((_QWORD *)this + 24) = 0;
  v4 = (DirectUI::DUIXmlParser **)(v2 + 1);
  if ( v2[1] )
    return 0;
  if ( (int)InitThread(2) < 0 )
    return 0;
  *((_DWORD *)v2 + 45) = 1;
  if ( (int)DirectUI::DUIXmlParser::Create(
              (struct DirectUI::DUIXmlParser **)v2 + 1,
              (struct DirectUI::Value *(*)(const unsigned __int16 *, void *))CLoadDui::StaticXMLGetSheetCB,
              v2,
              (void (*)(const unsigned __int16 *, const unsigned __int16 *, int, void *))CLoadDui::StaticXMLParserErrorCB,
              v2) < 0
    || (int)DirectUI::DUIXmlParser::SetXMLFromResource(*v4, 0x6Au, *v2, (HINSTANCE)&_ImageBase) < 0
    || (int)DirectUI::DUIXmlParser::CreateElement(*v4, L"main", 0, 0, &v7, v3) < 0 )
  {
    return 0;
  }
  DirectUI::Element::EndDefer(*v3, v7);
  CreateDUIWrapper(*v3, &v6);
  return (const unsigned __int16 *)v6;
}

```

## disassembly

```asm
0x1800026c8  mov     rax, rsp
0x1800026cb  mov     [rax+18h], rbx
0x1800026cf  mov     [rax+20h], rsi
0x1800026d3  mov     [rax+10h], edx
0x1800026d6  push    rdi
0x1800026d7  sub     rsp, 30h
0x1800026db  mov     rdi, [rcx+18h]
0x1800026df  lea     rbx, [rcx+0C0h]
0x1800026e6  mov     qword ptr [rax+8], 0
0x1800026ee  mov     dword ptr [rax+10h], 0
0x1800026f5  mov     qword ptr [rbx], 0
0x1800026fc  lea     rsi, [rdi+8]
0x180002700  cmp     qword ptr [rsi], 0
0x180002704  jnz     loc_1800027B1
0x18000270a  mov     ecx, 2
0x18000270f  call    cs:__imp_InitThread
0x180002715  test    eax, eax
0x180002717  js      loc_1800027B1
0x18000271d  lea     r9, ?StaticXMLParserErrorCB@CLoadDui@@CAXPEBG0HPEAX@Z; CLoadDui::StaticXMLParserErrorCB(ushort const *,ushort const *,int,void *)
0x180002724  mov     dword ptr [rdi+0B4h], 1
0x18000272e  mov     r8, rdi
0x180002731  mov     [rsp+38h+var_18], rdi
0x180002736  lea     rdx, ?StaticXMLGetSheetCB@CLoadDui@@CAPEAVValue@DirectUI@@PEBGPEAX@Z; CLoadDui::StaticXMLGetSheetCB(ushort const *,void *)
0x18000273d  mov     rcx, rsi
0x180002740  call    cs:__imp_?Create@DUIXmlParser@DirectUI@@SAJPEAPEAV12@P6APEAVValue@2@PEBGPEAX@Z2P6AX11H2@Z2@Z; DirectUI::DUIXmlParser::Create(DirectUI::DUIXmlParser * *,DirectUI::Value * (*)(ushort const *,void *),void *,void (*)(ushort const *,ushort const *,int,void *),void *)
0x180002746  test    eax, eax
0x180002748  js      short loc_1800027B1
0x18000274a  mov     r8, [rdi]
0x18000274d  lea     r9, __ImageBase
0x180002754  mov     rcx, [rsi]
0x180002757  mov     edx, 6Ah ; 'j'
0x18000275c  call    cs:__imp_?SetXMLFromResource@DUIXmlParser@DirectUI@@QEAAJIPEAUHINSTANCE__@@0@Z; DirectUI::DUIXmlParser::SetXMLFromResource(uint,HINSTANCE__ *,HINSTANCE__ *)
0x180002762  test    eax, eax
0x180002764  js      short loc_1800027B1
0x180002766  mov     rcx, [rsi]
0x180002769  lea     rax, [rsp+38h+arg_8]
0x18000276e  mov     [rsp+38h+var_10], rbx
0x180002773  lea     rdx, aMain; "main"
0x18000277a  xor     r9d, r9d
0x18000277d  mov     [rsp+38h+var_18], rax
0x180002782  xor     r8d, r8d
0x180002785  call    cs:__imp_?CreateElement@DUIXmlParser@DirectUI@@QEAAJPEBGPEAVElement@2@1PEAKPEAPEAV32@@Z; DirectUI::DUIXmlParser::CreateElement(ushort const *,DirectUI::Element *,DirectUI::Element *,ulong *,DirectUI::Element * *)
0x18000278b  test    eax, eax
0x18000278d  js      short loc_1800027B1
0x18000278f  mov     edx, [rsp+38h+arg_8]
0x180002793  mov     rcx, [rbx]
0x180002796  call    cs:__imp_?EndDefer@Element@DirectUI@@QEAAXK@Z; DirectUI::Element::EndDefer(ulong)
0x18000279c  mov     rcx, [rbx]
0x18000279f  lea     rdx, [rsp+38h+arg_0]
0x1800027a4  call    cs:__imp_CreateDUIWrapper
0x1800027aa  mov     rax, [rsp+38h+arg_0]
0x1800027af  jmp     short loc_1800027B3
0x1800027b1  xor     eax, eax
0x1800027b3  mov     rbx, [rsp+38h+arg_10]
0x1800027b8  mov     rsi, [rsp+38h+arg_18]
0x1800027bd  add     rsp, 30h
0x1800027c1  pop     rdi
0x1800027c2  retn
```
