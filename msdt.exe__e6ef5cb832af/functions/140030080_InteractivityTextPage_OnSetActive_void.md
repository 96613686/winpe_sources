# InteractivityTextPage::OnSetActive(void)

- ea: `0x140030080`
- end: `0x1400301a8`
- name: `?OnSetActive@InteractivityTextPage@@MEAA_JXZ`
- size: `296`
- prototype: `__int64 __fastcall(InteractivityTextPage *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task`

## callers

- `0x140017d20`

## callees

- `0x14000e6bc`
- `0x14000e978`
- `0x1400108b0`
- `0x140020420`
- `0x14002fc60`
- `0x140030080`

## import_xrefs

- `DUI70!?GetVisible@Element@DirectUI@@QEAA_NXZ` at `0x14003010b`
- `DUI70!?GetVisible@Element@DirectUI@@QEAA_NXZ` at `0x14003010b`
- `DUI70!?EndDefer@Element@DirectUI@@QEAAXK@Z` at `0x140030192`
- `DUI70!?EndDefer@Element@DirectUI@@QEAAXK@Z` at `0x140030192`
- `DUI70!?GetElement@TaskPage@DirectUI@@IEAAPEAVElement@2@XZ` at `0x140030089`
- `DUI70!?GetElement@TaskPage@DirectUI@@IEAAPEAVElement@2@XZ` at `0x140030089`
- `DUI70!?StartDefer@Element@DirectUI@@QEAAXPEAK@Z` at `0x1400300aa`
- `DUI70!?StartDefer@Element@DirectUI@@QEAAXPEAK@Z` at `0x1400300aa`

## string_xrefs

- `0x14003012e`: `linkContainer`
- `0x1400300eb`: `linkInteraction`
- `0x1400300c0`: `flushLinkContainer`
- `0x14003014f`: `flushLinkContainer`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall InteractivityTextPage::OnSetActive(InteractivityTextPage *this)
{
  int NamedElement; // eax
  int v3; // r9d
  DirectUI::Element *Element; // [rsp+30h] [rbp-18h]
  unsigned int v6[4]; // [rsp+38h] [rbp-10h] BYREF
  struct DirectUI::Element *v7; // [rsp+58h] [rbp+10h] BYREF

  Element = DirectUI::TaskPage::GetElement(this);
  v6[0] = 0;
  DirectUI::Element::StartDefer(Element, v6);
  v7 = 0;
  NamedElement = WizardPage::HideNamedElement(this, L"flushLinkContainer");
  if ( NamedElement < 0 )
  {
    v3 = 3718;
LABEL_12:
    SdpDebugPrint(1u, "Dwz ERROR: %s:%d - hr = 0x%08X\n", "InteractivityTextPage::OnSetActive", v3, NamedElement);
    goto LABEL_13;
  }
  InteractivityPage::OnSetActive(this);
  NamedElement = WizardPage::GetNamedElement(this, L"linkInteraction", &v7);
  if ( NamedElement < 0 )
  {
    v3 = 3723;
    goto LABEL_12;
  }
  if ( DirectUI::Element::GetVisible(v7) && *((_DWORD *)this + 46) && !*((_QWORD *)this + 18) )
  {
    NamedElement = WizardPage::HideNamedElement(this, L"linkContainer");
    if ( NamedElement >= 0 )
    {
      NamedElement = WizardPage::ShowNamedElement(this, L"flushLinkContainer", 1);
      if ( NamedElement >= 0 )
        goto LABEL_13;
      v3 = 3730;
    }
    else
    {
      v3 = 3727;
    }
    goto LABEL_12;
  }
LABEL_13:
  if ( v6[0] )
    DirectUI::Element::EndDefer(Element, v6[0]);
  return 0;
}

```

## disassembly

```asm
0x140030080  push    rbx
0x140030082  sub     rsp, 40h
0x140030086  mov     rbx, rcx
0x140030089  call    cs:__imp_?GetElement@TaskPage@DirectUI@@IEAAPEAVElement@2@XZ; DirectUI::TaskPage::GetElement(void)
0x140030090  nop     dword ptr [rax+rax+00h]
0x140030095  mov     [rsp+48h+var_18], rax
0x14003009a  mov     [rsp+48h+var_10], 0
0x1400300a2  lea     rdx, [rsp+48h+var_10]
0x1400300a7  mov     rcx, rax
0x1400300aa  call    cs:__imp_?StartDefer@Element@DirectUI@@QEAAXPEAK@Z; DirectUI::Element::StartDefer(ulong *)
0x1400300b1  nop     dword ptr [rax+rax+00h]
0x1400300b6  nop
0x1400300b7  mov     [rsp+48h+arg_8], 0
0x1400300c0  lea     rdx, aFlushlinkconta; "flushLinkContainer"
0x1400300c7  mov     rcx, rbx; this
0x1400300ca  call    ?HideNamedElement@WizardPage@@IEAAJPEBG@Z; WizardPage::HideNamedElement(ushort const *)
0x1400300cf  test    eax, eax
0x1400300d1  jns     short loc_1400300DE
0x1400300d3  mov     r9d, 0E86h
0x1400300d9  jmp     loc_140030168
0x1400300de  mov     rcx, rbx; this
0x1400300e1  call    ?OnSetActive@InteractivityPage@@MEAA_JXZ; InteractivityPage::OnSetActive(void)
0x1400300e6  lea     r8, [rsp+48h+arg_8]; struct DirectUI::Element **
0x1400300eb  lea     rdx, aLinkinteractio; "linkInteraction"
0x1400300f2  mov     rcx, rbx; this
0x1400300f5  call    ?GetNamedElement@WizardPage@@QEAAJPEBGPEAPEAVElement@DirectUI@@@Z; WizardPage::GetNamedElement(ushort const *,DirectUI::Element * *)
0x1400300fa  test    eax, eax
0x1400300fc  jns     short loc_140030106
0x1400300fe  mov     r9d, 0E8Bh
0x140030104  jmp     short loc_140030168
0x140030106  mov     rcx, [rsp+48h+arg_8]
0x14003010b  call    cs:__imp_?GetVisible@Element@DirectUI@@QEAA_NXZ; DirectUI::Element::GetVisible(void)
0x140030112  nop     dword ptr [rax+rax+00h]
0x140030117  test    al, al
0x140030119  jz      short loc_140030185
0x14003011b  cmp     dword ptr [rbx+0B8h], 0
0x140030122  jz      short loc_140030185
0x140030124  cmp     qword ptr [rbx+90h], 0
0x14003012c  jnz     short loc_140030185
0x14003012e  lea     rdx, aLinkcontainer; "linkContainer"
0x140030135  mov     rcx, rbx; this
0x140030138  call    ?HideNamedElement@WizardPage@@IEAAJPEBG@Z; WizardPage::HideNamedElement(ushort const *)
0x14003013d  test    eax, eax
0x14003013f  jns     short loc_140030149
0x140030141  mov     r9d, 0E8Fh
0x140030147  jmp     short loc_140030168
0x140030149  mov     r8d, 1; int
0x14003014f  lea     rdx, aFlushlinkconta; "flushLinkContainer"
0x140030156  mov     rcx, rbx; this
0x140030159  call    ?ShowNamedElement@WizardPage@@IEAAJPEBGH@Z; WizardPage::ShowNamedElement(ushort const *,int)
0x14003015e  test    eax, eax
0x140030160  jns     short loc_140030185
0x140030162  mov     r9d, 0E92h
0x140030168  mov     [rsp+48h+var_28], eax
0x14003016c  lea     r8, aInteractivityt_2; "InteractivityTextPage::OnSetActive"
0x140030173  lea     rdx, aDwzErrorSDHr0x; "Dwz ERROR: %s:%d - hr = 0x%08X\n"
0x14003017a  mov     ecx, 1; Level
0x14003017f  call    ?SdpDebugPrint@@YAXKPEBDZZ; SdpDebugPrint(ulong,char const *,...)
0x140030184  nop
0x140030185  mov     edx, [rsp+48h+var_10]
0x140030189  test    edx, edx
0x14003018b  jz      short loc_14003019F
0x14003018d  mov     rcx, [rsp+48h+var_18]
0x140030192  call    cs:__imp_?EndDefer@Element@DirectUI@@QEAAXK@Z; DirectUI::Element::EndDefer(ulong)
0x140030199  nop     dword ptr [rax+rax+00h]
0x14003019e  nop
0x14003019f  xor     eax, eax
0x1400301a1  add     rsp, 40h
0x1400301a5  pop     rbx
0x1400301a6  retn
```
