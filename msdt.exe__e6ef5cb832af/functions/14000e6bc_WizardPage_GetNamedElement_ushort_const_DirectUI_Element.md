# WizardPage::GetNamedElement(ushort const *,DirectUI::Element * *)

- ea: `0x14000e6bc`
- end: `0x14000e726`
- name: `?GetNamedElement@WizardPage@@QEAAJPEBGPEAPEAVElement@DirectUI@@@Z`
- size: `106`
- prototype: `__int64 __fastcall(WizardPage *__hidden this, const unsigned __int16 *, struct DirectUI::Element **)`
- caller_count: `47`
- callee_count: `1`
- tags: `service_task`

## callers

- `0x14000e300`
- `0x14000e978`
- `0x14000f0e0`
- `0x140010680`
- `0x1400108b0`
- `0x140014d18`
- `0x140015490`
- `0x140015580`
- `0x140015d10`
- `0x140015ea0`
- `0x1400160c0`
- `0x1400163c0`
- `0x140016520`
- `0x140016ab0`
- `0x140016c80`
- `0x1400177b0`
- `0x140017ef0`
- `0x1400186b4`
- `0x140018f6c`
- `0x140019710`
- `0x14001a03c`
- `0x14001a290`
- `0x14002b910`
- `0x14002e310`
- `0x14002e470`
- `0x14002e710`
- `0x14002e820`
- `0x14002e900`
- `0x14002ea60`
- `0x14002f270`
- `0x14002f890`
- `0x14002fc60`
- `0x140030080`
- `0x140030410`
- `0x1400309e0`
- `0x14003285c`
- `0x14003a760`
- `0x14003a9d0`
- `0x14003aaa0`
- `0x14003abe0`
- `0x14003adc0`
- `0x14003afa0`
- `0x14003b260`
- `0x14003b500`
- `0x14003bfc0`
- `0x140047700`
- `0x140047900`

## callees

- `0x14000e6bc`

## import_xrefs

- `DUI70!StrToID` at `0x14000e6e3`
- `DUI70!StrToID` at `0x14000e6e3`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x14000e6f5`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x14000e6f5`
- `DUI70!?GetElement@TaskPage@DirectUI@@IEAAPEAVElement@2@XZ` at `0x14000e6d1`
- `DUI70!?GetElement@TaskPage@DirectUI@@IEAAPEAVElement@2@XZ` at `0x14000e6d1`

## pseudocode

```c
__int64 __fastcall WizardPage::GetNamedElement(
        WizardPage *this,
        const unsigned __int16 *a2,
        struct DirectUI::Element **a3)
{
  DirectUI::Element *Element; // rbx
  unsigned __int16 v6; // ax
  struct DirectUI::Element *Descendent; // rcx
  __int64 result; // rax

  Element = DirectUI::TaskPage::GetElement(this);
  v6 = StrToID(a2);
  Descendent = DirectUI::Element::FindDescendent(Element, v6);
  if ( !Descendent )
    return 2147500037LL;
  result = 0;
  *a3 = Descendent;
  return result;
}

```

## disassembly

```asm
0x14000e6bc  mov     [rsp+arg_0], rbx
0x14000e6c1  mov     [rsp+arg_8], rsi
0x14000e6c6  push    rdi
0x14000e6c7  sub     rsp, 20h
0x14000e6cb  mov     rsi, r8
0x14000e6ce  mov     rdi, rdx
0x14000e6d1  call    cs:__imp_?GetElement@TaskPage@DirectUI@@IEAAPEAVElement@2@XZ; DirectUI::TaskPage::GetElement(void)
0x14000e6d8  nop     dword ptr [rax+rax+00h]
0x14000e6dd  mov     rcx, rdi
0x14000e6e0  mov     rbx, rax
0x14000e6e3  call    cs:__imp_StrToID
0x14000e6ea  nop     dword ptr [rax+rax+00h]
0x14000e6ef  movzx   edx, ax
0x14000e6f2  mov     rcx, rbx
0x14000e6f5  call    cs:__imp_?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z; DirectUI::Element::FindDescendent(ushort)
0x14000e6fc  nop     dword ptr [rax+rax+00h]
0x14000e701  mov     rcx, rax
0x14000e704  test    rax, rax
0x14000e707  jnz     short loc_14000E710
0x14000e709  mov     eax, 80004005h
0x14000e70e  jmp     short loc_14000E715
0x14000e710  xor     eax, eax
0x14000e712  mov     [rsi], rcx
0x14000e715  mov     rbx, [rsp+28h+arg_0]
0x14000e71a  mov     rsi, [rsp+28h+arg_8]
0x14000e71f  add     rsp, 20h
0x14000e723  pop     rdi
0x14000e724  retn
```
