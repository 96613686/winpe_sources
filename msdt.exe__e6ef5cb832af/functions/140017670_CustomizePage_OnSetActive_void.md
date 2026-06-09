# CustomizePage::OnSetActive(void)

- ea: `0x140017670`
- end: `0x14001779b`
- name: `?OnSetActive@CustomizePage@@MEAA_JXZ`
- size: `299`
- prototype: `__int64 __fastcall(CustomizePage *__hidden this)`
- caller_count: `0`
- callee_count: `8`
- tags: `registry_config`

## callees

- `0x14000f480`
- `0x140010a10`
- `0x140014d18`
- `0x140017670`
- `0x14001834c`
- `0x1400184a0`
- `0x140020420`
- `0x140063010`

## import_xrefs

- `DUI70!?Destroy@DUIXmlParser@DirectUI@@QEAAXXZ` at `0x140017761`
- `DUI70!?Destroy@DUIXmlParser@DirectUI@@QEAAXXZ` at `0x140017761`
- `DUI70!?EndDefer@Element@DirectUI@@QEAAXK@Z` at `0x140017780`
- `DUI70!?EndDefer@Element@DirectUI@@QEAAXK@Z` at `0x140017780`
- `DUI70!?StartDefer@Element@DirectUI@@QEAAXPEAK@Z` at `0x1400176a2`
- `DUI70!?StartDefer@Element@DirectUI@@QEAAXPEAK@Z` at `0x1400176a2`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CustomizePage::OnSetActive(CustomizePage *this)
{
  int v2; // eax
  int v3; // r9d
  DirectUI::Element *v5; // [rsp+30h] [rbp-10h]
  unsigned int v6; // [rsp+38h] [rbp-8h] BYREF
  int v7; // [rsp+50h] [rbp+10h] BYREF
  struct DirectUI::DUIXmlParser *v8; // [rsp+58h] [rbp+18h] BYREF

  v7 = 0;
  v8 = 0;
  v5 = (DirectUI::Element *)*((_QWORD *)this + 8);
  v6 = 0;
  DirectUI::Element::StartDefer(v5, &v6);
  WizardPage::StartRetireBannerTipTest(this, 16);
  WizardPage::OnSetActive(this);
  v2 = (*(__int64 (__fastcall **)(CustomizePage *, struct DirectUI::DUIXmlParser **))(*(_QWORD *)this + 56LL))(
         this,
         &v8);
  if ( v2 < 0 )
  {
    v3 = 2724;
LABEL_3:
    SdpDebugPrint(1u, "Dwz ERROR: %s:%d - hr = 0x%08X\n", "CustomizePage::OnSetActive", v3, v2);
    goto LABEL_11;
  }
  v2 = CustomizePage::AddRootCauses(this, v8);
  if ( v2 < 0 )
  {
    v3 = 2730;
    goto LABEL_3;
  }
  v2 = CustomizePage::ResetCheckboxes(this);
  if ( v2 < 0 )
  {
    v3 = 2733;
    goto LABEL_3;
  }
  v2 = CustomizePage::ResolutionsChecked(this, &v7);
  if ( v2 < 0 )
  {
    v3 = 2736;
    goto LABEL_3;
  }
  *((_DWORD *)Config + 11) = 1;
  *((_DWORD *)this + 20) = 55;
LABEL_11:
  if ( v8 )
  {
    DirectUI::DUIXmlParser::Destroy(v8);
    v8 = 0;
  }
  if ( v6 )
    DirectUI::Element::EndDefer(v5, v6);
  return 0;
}

```

## disassembly

```asm
0x140017670  mov     [rsp-8+arg_10], rbx
0x140017675  push    rbp
0x140017676  mov     rbp, rsp
0x140017679  sub     rsp, 40h
0x14001767d  mov     rbx, rcx
0x140017680  mov     [rbp+arg_0], 0
0x140017687  mov     [rbp+arg_8], 0
0x14001768f  mov     rcx, [rcx+40h]
0x140017693  mov     [rbp+var_10], rcx
0x140017697  mov     [rbp+var_8], 0
0x14001769e  lea     rdx, [rbp+var_8]
0x1400176a2  call    cs:__imp_?StartDefer@Element@DirectUI@@QEAAXPEAK@Z; DirectUI::Element::StartDefer(ulong *)
0x1400176a9  nop     dword ptr [rax+rax+00h]
0x1400176ae  nop
0x1400176af  mov     edx, 10h
0x1400176b4  mov     rcx, rbx
0x1400176b7  call    ?StartRetireBannerTipTest@WizardPage@@IEAAXW4PageNames@@@Z; WizardPage::StartRetireBannerTipTest(PageNames)
0x1400176bc  mov     rcx, rbx; this
0x1400176bf  call    ?OnSetActive@WizardPage@@MEAA_JXZ; WizardPage::OnSetActive(void)
0x1400176c4  mov     rax, [rbx]
0x1400176c7  lea     rdx, [rbp+arg_8]
0x1400176cb  mov     rcx, rbx
0x1400176ce  mov     rax, [rax+38h]
0x1400176d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400176d7  test    eax, eax
0x1400176d9  jns     short loc_1400176FF
0x1400176db  mov     r9d, 0AA4h
0x1400176e1  mov     [rsp+40h+var_20], eax
0x1400176e5  lea     r8, aCustomizepageO_0; "CustomizePage::OnSetActive"
0x1400176ec  lea     rdx, aDwzErrorSDHr0x; "Dwz ERROR: %s:%d - hr = 0x%08X\n"
0x1400176f3  mov     ecx, 1; Level
0x1400176f8  call    ?SdpDebugPrint@@YAXKPEBDZZ; SdpDebugPrint(ulong,char const *,...)
0x1400176fd  jmp     short loc_140017758
0x1400176ff  mov     rdx, [rbp+arg_8]; struct DirectUI::DUIXmlParser *
0x140017703  mov     rcx, rbx; this
0x140017706  call    ?AddRootCauses@CustomizePage@@IEAAJPEAVDUIXmlParser@DirectUI@@@Z; CustomizePage::AddRootCauses(DirectUI::DUIXmlParser *)
0x14001770b  test    eax, eax
0x14001770d  jns     short loc_140017717
0x14001770f  mov     r9d, 0AAAh
0x140017715  jmp     short loc_1400176E1
0x140017717  mov     rcx, rbx; this
0x14001771a  call    ?ResetCheckboxes@CustomizePage@@IEAAJXZ; CustomizePage::ResetCheckboxes(void)
0x14001771f  test    eax, eax
0x140017721  jns     short loc_14001772B
0x140017723  mov     r9d, 0AADh
0x140017729  jmp     short loc_1400176E1
0x14001772b  lea     rdx, [rbp+arg_0]; int *
0x14001772f  mov     rcx, rbx; this
0x140017732  call    ?ResolutionsChecked@CustomizePage@@IEAAJPEAH@Z; CustomizePage::ResolutionsChecked(int *)
0x140017737  test    eax, eax
0x140017739  jns     short loc_140017743
0x14001773b  mov     r9d, 0AB0h
0x140017741  jmp     short loc_1400176E1
0x140017743  mov     rax, cs:?Config@@3PEAVConfiguration@@EA; Configuration * Config
0x14001774a  mov     dword ptr [rax+2Ch], 1
0x140017751  mov     dword ptr [rbx+50h], 37h ; '7'
0x140017758  mov     rcx, [rbp+arg_8]
0x14001775c  test    rcx, rcx
0x14001775f  jz      short loc_140017775
0x140017761  call    cs:__imp_?Destroy@DUIXmlParser@DirectUI@@QEAAXXZ; DirectUI::DUIXmlParser::Destroy(void)
0x140017768  nop     dword ptr [rax+rax+00h]
0x14001776d  mov     [rbp+arg_8], 0
0x140017775  mov     edx, [rbp+var_8]
0x140017778  test    edx, edx
0x14001777a  jz      short loc_14001778D
0x14001777c  mov     rcx, [rbp+var_10]
0x140017780  call    cs:__imp_?EndDefer@Element@DirectUI@@QEAAXK@Z; DirectUI::Element::EndDefer(ulong)
0x140017787  nop     dword ptr [rax+rax+00h]
0x14001778c  nop
0x14001778d  xor     eax, eax
0x14001778f  mov     rbx, [rsp+40h+arg_10]
0x140017794  add     rsp, 40h
0x140017798  pop     rbp
0x140017799  retn
```
