# SupportKeyPage::OnListenedInput(DirectUI::Element *,DirectUI::InputEvent *)

- ea: `0x14003b1c0`
- end: `0x14003b24d`
- name: `?OnListenedInput@SupportKeyPage@@MEAAXPEAVElement@DirectUI@@PEAUInputEvent@3@@Z`
- size: `141`
- prototype: `void __fastcall(SupportKeyPage *__hidden this, struct DirectUI::Element *, struct DirectUI::InputEvent *)`
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, installer_update`

## callees

- `0x140020420`
- `0x14003b1c0`
- `0x14003cd40`

## import_xrefs

- `DUI70!StrToID` at `0x14003b1eb`
- `DUI70!StrToID` at `0x14003b1eb`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x14003b1fd`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x14003b1fd`
- `DUI70!?GetElement@TaskPage@DirectUI@@IEAAPEAVElement@2@XZ` at `0x14003b1d5`
- `DUI70!?GetElement@TaskPage@DirectUI@@IEAAPEAVElement@2@XZ` at `0x14003b1d5`

## pseudocode

```c
void __fastcall SupportKeyPage::OnListenedInput(
        SupportKeyPage *this,
        struct DirectUI::Element *a2,
        struct DirectUI::Element **a3)
{
  DirectUI::Element *Element; // rbx
  unsigned __int16 v6; // ax
  int Button; // eax

  Element = DirectUI::TaskPage::GetElement(this);
  v6 = StrToID(L"edit");
  if ( *a3 == DirectUI::Element::FindDescendent(Element, v6) )
  {
    Button = SupportKeyPage::SetupNextButton(this);
    if ( Button < 0 )
      SdpDebugPrint(1u, "Dwz ERROR: %s:%d - hr = 0x%08X\n", "SupportKeyPage::OnListenedInput", 315, Button);
  }
}

```

## disassembly

```asm
0x14003b1c0  mov     [rsp+arg_0], rbx
0x14003b1c5  mov     [rsp+arg_8], rsi
0x14003b1ca  push    rdi
0x14003b1cb  sub     rsp, 30h
0x14003b1cf  mov     rdi, r8
0x14003b1d2  mov     rsi, rcx
0x14003b1d5  call    cs:__imp_?GetElement@TaskPage@DirectUI@@IEAAPEAVElement@2@XZ; DirectUI::TaskPage::GetElement(void)
0x14003b1dc  nop     dword ptr [rax+rax+00h]
0x14003b1e1  lea     rcx, ClassName; "edit"
0x14003b1e8  mov     rbx, rax
0x14003b1eb  call    cs:__imp_StrToID
0x14003b1f2  nop     dword ptr [rax+rax+00h]
0x14003b1f7  movzx   edx, ax
0x14003b1fa  mov     rcx, rbx
0x14003b1fd  call    cs:__imp_?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z; DirectUI::Element::FindDescendent(ushort)
0x14003b204  nop     dword ptr [rax+rax+00h]
0x14003b209  cmp     [rdi], rax
0x14003b20c  jnz     short loc_14003B23C
0x14003b20e  mov     rcx, rsi; this
0x14003b211  call    ?SetupNextButton@SupportKeyPage@@IEAAJXZ; SupportKeyPage::SetupNextButton(void)
0x14003b216  test    eax, eax
0x14003b218  jns     short loc_14003B23C
0x14003b21a  mov     r9d, 13Bh
0x14003b220  mov     [rsp+38h+var_18], eax
0x14003b224  lea     r8, aSupportkeypage_6; "SupportKeyPage::OnListenedInput"
0x14003b22b  mov     ecx, 1; Level
0x14003b230  lea     rdx, aDwzErrorSDHr0x; "Dwz ERROR: %s:%d - hr = 0x%08X\n"
0x14003b237  call    ?SdpDebugPrint@@YAXKPEBDZZ; SdpDebugPrint(ulong,char const *,...)
0x14003b23c  mov     rbx, [rsp+38h+arg_0]
0x14003b241  mov     rsi, [rsp+38h+arg_8]
0x14003b246  add     rsp, 30h
0x14003b24a  pop     rdi
0x14003b24b  retn
```
