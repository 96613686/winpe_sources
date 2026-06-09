# FinalLinksPage::OnQueryInitialFocus(void)

- ea: `0x14001add0`
- end: `0x14001ae4d`
- name: `?OnQueryInitialFocus@FinalLinksPage@@MEAAPEAVElement@DirectUI@@XZ`
- size: `125`
- prototype: `struct DirectUI::Element *__fastcall(FinalLinksPage *__hidden this)`
- caller_count: `0`
- callee_count: `2`
- tags: `service_task`

## callees

- `0x14001add0`
- `0x140063010`

## import_xrefs

- `DUI70!?GetVisible@Element@DirectUI@@QEAA_NXZ` at `0x14001ae2a`
- `DUI70!?GetVisible@Element@DirectUI@@QEAA_NXZ` at `0x14001ae2a`
- `DUI70!StrToID` at `0x14001ae01`
- `DUI70!StrToID` at `0x14001ae01`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x14001ae13`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x14001ae13`
- `DUI70!?GetElement@TaskPage@DirectUI@@IEAAPEAVElement@2@XZ` at `0x14001addd`
- `DUI70!?GetElement@TaskPage@DirectUI@@IEAAPEAVElement@2@XZ` at `0x14001addd`

## pseudocode

```c
struct DirectUI::Element *__fastcall FinalLinksPage::OnQueryInitialFocus(FinalLinksPage *this)
{
  DirectUI::Element *Element; // rdi
  __int64 v3; // rax
  unsigned __int16 v4; // ax
  DirectUI::Element *Descendent; // rax
  DirectUI::Element *v6; // rbx

  Element = DirectUI::TaskPage::GetElement(this);
  v3 = (*(__int64 (__fastcall **)(FinalLinksPage *))(*(_QWORD *)this + 288LL))(this);
  v4 = StrToID(v3);
  Descendent = DirectUI::Element::FindDescendent(Element, v4);
  v6 = Descendent;
  if ( Descendent )
    return (struct DirectUI::Element *)(-(__int64)DirectUI::Element::GetVisible(Descendent)
                                      & (unsigned __int64)Descendent);
  return v6;
}

```

## disassembly

```asm
0x14001add0  mov     [rsp+arg_0], rbx
0x14001add5  push    rdi
0x14001add6  sub     rsp, 20h
0x14001adda  mov     rbx, rcx
0x14001addd  call    cs:__imp_?GetElement@TaskPage@DirectUI@@IEAAPEAVElement@2@XZ; DirectUI::TaskPage::GetElement(void)
0x14001ade4  nop     dword ptr [rax+rax+00h]
0x14001ade9  mov     rdx, [rbx]
0x14001adec  mov     rcx, rbx
0x14001adef  mov     rdi, rax
0x14001adf2  mov     rax, [rdx+120h]
0x14001adf9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001adfe  mov     rcx, rax
0x14001ae01  call    cs:__imp_StrToID
0x14001ae08  nop     dword ptr [rax+rax+00h]
0x14001ae0d  movzx   edx, ax
0x14001ae10  mov     rcx, rdi
0x14001ae13  call    cs:__imp_?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z; DirectUI::Element::FindDescendent(ushort)
0x14001ae1a  nop     dword ptr [rax+rax+00h]
0x14001ae1f  mov     rbx, rax
0x14001ae22  test    rax, rax
0x14001ae25  jz      short loc_14001AE3E
0x14001ae27  mov     rcx, rax
0x14001ae2a  call    cs:__imp_?GetVisible@Element@DirectUI@@QEAA_NXZ; DirectUI::Element::GetVisible(void)
0x14001ae31  nop     dword ptr [rax+rax+00h]
0x14001ae36  neg     al
0x14001ae38  sbb     rcx, rcx
0x14001ae3b  and     rbx, rcx
0x14001ae3e  mov     rax, rbx
0x14001ae41  mov     rbx, [rsp+28h+arg_0]
0x14001ae46  add     rsp, 20h
0x14001ae4a  pop     rdi
0x14001ae4b  retn
```
