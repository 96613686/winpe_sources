# OSKDuiFrame::~OSKDuiFrame(void)

- ea: `0x14000ec48`
- end: `0x14000ec7c`
- name: `??1OSKDuiFrame@@UEAA@XZ`
- size: `52`
- prototype: `void __fastcall(OSKDuiFrame *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x14000ec90`

## callees

- `0x14000ec48`

## import_xrefs

- `DUI70!?Destroy@DUIXmlParser@DirectUI@@QEAAXXZ` at `0x14000ec67`
- `DUI70!?Destroy@DUIXmlParser@DirectUI@@QEAAXXZ` at `0x14000ec67`
- `DUI70!??1HWNDElement@DirectUI@@UEAA@XZ` at `0x14000ec75`

## pseudocode

```c
void __fastcall OSKDuiFrame::~OSKDuiFrame(OSKDuiFrame *this)
{
  DirectUI::DUIXmlParser *v2; // rcx

  *(_QWORD *)this = &OSKDuiFrame::`vftable';
  v2 = (DirectUI::DUIXmlParser *)*((_QWORD *)this + 35);
  if ( v2 )
    DirectUI::DUIXmlParser::Destroy(v2);
  DirectUI::HWNDElement::~HWNDElement(this);
}

```

## disassembly

```asm
0x14000ec48  push    rbx
0x14000ec4a  sub     rsp, 20h
0x14000ec4e  mov     rbx, rcx
0x14000ec51  lea     rax, ??_7OSKDuiFrame@@6B@; const OSKDuiFrame::`vftable'
0x14000ec58  mov     [rcx], rax
0x14000ec5b  mov     rcx, [rcx+118h]
0x14000ec62  test    rcx, rcx
0x14000ec65  jz      short loc_14000EC6D
0x14000ec67  call    cs:__imp_?Destroy@DUIXmlParser@DirectUI@@QEAAXXZ; DirectUI::DUIXmlParser::Destroy(void)
0x14000ec6d  mov     rcx, rbx
0x14000ec70  add     rsp, 20h
0x14000ec74  pop     rbx
0x14000ec75  jmp     cs:__imp_??1HWNDElement@DirectUI@@UEAA@XZ; DirectUI::HWNDElement::~HWNDElement(void)
```
