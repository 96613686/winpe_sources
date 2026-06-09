# DetailsPage::OnSetActive(void)

- ea: `0x1400177b0`
- end: `0x140017918`
- name: `?OnSetActive@DetailsPage@@MEAA_JXZ`
- size: `360`
- prototype: `__int64 __fastcall(DetailsPage *__hidden this)`
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, service_task`

## callees

- `0x14000e0f0`
- `0x14000e6bc`
- `0x14000f480`
- `0x1400177b0`
- `0x140020420`

## import_xrefs

- `USER32!PostMessageW` at `0x1400178e5`
- `USER32!PostMessageW` at `0x1400178e5`
- `DUI70!?EndDefer@Element@DirectUI@@QEAAXK@Z` at `0x1400178fd`
- `DUI70!?EndDefer@Element@DirectUI@@QEAAXK@Z` at `0x1400178fd`
- `DUI70!?GetElement@TaskPage@DirectUI@@IEAAPEAVElement@2@XZ` at `0x1400177d8`
- `DUI70!?GetElement@TaskPage@DirectUI@@IEAAPEAVElement@2@XZ` at `0x1400177d8`
- `DUI70!?StartDefer@Element@DirectUI@@QEAAXPEAK@Z` at `0x1400177f6`
- `DUI70!?StartDefer@Element@DirectUI@@QEAAXPEAK@Z` at `0x1400177f6`
- `DUI70!?GetParentHWND@TaskPage@DirectUI@@QEAAPEAUHWND__@@XZ` at `0x1400178cb`
- `DUI70!?GetParentHWND@TaskPage@DirectUI@@QEAAPEAUHWND__@@XZ` at `0x1400178cb`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall DetailsPage::OnSetActive(DetailsPage *this)
{
  int NamedElement; // eax
  int v3; // r9d
  struct DirectUI::Element *v4; // rcx
  HWND ParentHWND; // rax
  DirectUI::Element *Element; // [rsp+30h] [rbp-10h]
  unsigned int v8; // [rsp+38h] [rbp-8h] BYREF
  struct DirectUI::Element *v9; // [rsp+58h] [rbp+18h] BYREF
  struct DirectUI::Element *v10; // [rsp+60h] [rbp+20h] BYREF
  struct DirectUI::Element *v11; // [rsp+68h] [rbp+28h] BYREF

  v9 = 0;
  v10 = 0;
  v11 = 0;
  Element = DirectUI::TaskPage::GetElement(this);
  v8 = 0;
  DirectUI::Element::StartDefer(Element, &v8);
  NamedElement = WizardPage::GetNamedElement(this, L"details", &v9);
  if ( NamedElement < 0 )
  {
    v3 = 3185;
LABEL_3:
    SdpDebugPrint(1u, "Dwz ERROR: %s:%d - hr = 0x%08X\n", "DetailsPage::OnSetActive", v3, NamedElement);
    goto LABEL_12;
  }
  NamedElement = WizardPage::GetNamedElement(this, L"forward", &v10);
  if ( NamedElement < 0 )
  {
    v3 = 3188;
    goto LABEL_3;
  }
  NamedElement = WizardPage::GetNamedElement(this, L"backward", &v11);
  if ( NamedElement < 0 )
  {
    v3 = 3191;
    goto LABEL_3;
  }
  v4 = v9;
  *((_QWORD *)v9 + 42) = v10;
  *((_QWORD *)v4 + 43) = v11;
  WizardPage::OnSetActive(this);
  if ( *((_DWORD *)Config + 66) == 10 )
  {
    NamedElement = WizardPage::CloseButton(this);
    if ( NamedElement < 0 )
    {
      v3 = 3202;
      goto LABEL_3;
    }
  }
  ParentHWND = DirectUI::TaskPage::GetParentHWND(this);
  PostMessageW(ParentHWND, 0x9E8u, 0, 0);
LABEL_12:
  if ( v8 )
    DirectUI::Element::EndDefer(Element, v8);
  return 0;
}

```

## disassembly

```asm
0x1400177b0  mov     [rsp-8+arg_0], rbx
0x1400177b5  push    rbp
0x1400177b6  mov     rbp, rsp
0x1400177b9  sub     rsp, 40h
0x1400177bd  mov     rbx, rcx
0x1400177c0  mov     [rbp+arg_8], 0
0x1400177c8  mov     [rbp+arg_10], 0
0x1400177d0  mov     [rbp+arg_18], 0
0x1400177d8  call    cs:__imp_?GetElement@TaskPage@DirectUI@@IEAAPEAVElement@2@XZ; DirectUI::TaskPage::GetElement(void)
0x1400177df  nop     dword ptr [rax+rax+00h]
0x1400177e4  mov     [rbp+var_10], rax
0x1400177e8  mov     [rbp+var_8], 0
0x1400177ef  lea     rdx, [rbp+var_8]
0x1400177f3  mov     rcx, rax
0x1400177f6  call    cs:__imp_?StartDefer@Element@DirectUI@@QEAAXPEAK@Z; DirectUI::Element::StartDefer(ulong *)
0x1400177fd  nop     dword ptr [rax+rax+00h]
0x140017802  nop
0x140017803  lea     r8, [rbp+arg_8]; struct DirectUI::Element **
0x140017807  lea     rdx, aDetails; "details"
0x14001780e  mov     rcx, rbx; this
0x140017811  call    ?GetNamedElement@WizardPage@@QEAAJPEBGPEAPEAVElement@DirectUI@@@Z; WizardPage::GetNamedElement(ushort const *,DirectUI::Element * *)
0x140017816  test    eax, eax
0x140017818  jns     short loc_140017841
0x14001781a  mov     r9d, 0C71h
0x140017820  mov     [rsp+40h+var_20], eax
0x140017824  lea     r8, aDetailspageOns; "DetailsPage::OnSetActive"
0x14001782b  lea     rdx, aDwzErrorSDHr0x; "Dwz ERROR: %s:%d - hr = 0x%08X\n"
0x140017832  mov     ecx, 1; Level
0x140017837  call    ?SdpDebugPrint@@YAXKPEBDZZ; SdpDebugPrint(ulong,char const *,...)
0x14001783c  jmp     loc_1400178F2
0x140017841  lea     r8, [rbp+arg_10]; struct DirectUI::Element **
0x140017845  lea     rdx, aForward; "forward"
0x14001784c  mov     rcx, rbx; this
0x14001784f  call    ?GetNamedElement@WizardPage@@QEAAJPEBGPEAPEAVElement@DirectUI@@@Z; WizardPage::GetNamedElement(ushort const *,DirectUI::Element * *)
0x140017854  test    eax, eax
0x140017856  jns     short loc_140017860
0x140017858  mov     r9d, 0C74h
0x14001785e  jmp     short loc_140017820
0x140017860  lea     r8, [rbp+arg_18]; struct DirectUI::Element **
0x140017864  lea     rdx, aBackward; "backward"
0x14001786b  mov     rcx, rbx; this
0x14001786e  call    ?GetNamedElement@WizardPage@@QEAAJPEBGPEAPEAVElement@DirectUI@@@Z; WizardPage::GetNamedElement(ushort const *,DirectUI::Element * *)
0x140017873  test    eax, eax
0x140017875  jns     short loc_14001787F
0x140017877  mov     r9d, 0C77h
0x14001787d  jmp     short loc_140017820
0x14001787f  mov     rcx, [rbp+arg_8]
0x140017883  mov     rax, [rbp+arg_10]
0x140017887  mov     [rcx+150h], rax
0x14001788e  mov     rax, [rbp+arg_18]
0x140017892  mov     [rcx+158h], rax
0x140017899  mov     rcx, rbx; this
0x14001789c  call    ?OnSetActive@WizardPage@@MEAA_JXZ; WizardPage::OnSetActive(void)
0x1400178a1  mov     rax, cs:?Config@@3PEAVConfiguration@@EA; Configuration * Config
0x1400178a8  cmp     dword ptr [rax+108h], 0Ah
0x1400178af  jnz     short loc_1400178C8
0x1400178b1  mov     rcx, rbx; this
0x1400178b4  call    ?CloseButton@WizardPage@@IEAAJXZ; WizardPage::CloseButton(void)
0x1400178b9  test    eax, eax
0x1400178bb  jns     short loc_1400178C8
0x1400178bd  mov     r9d, 0C82h
0x1400178c3  jmp     loc_140017820
0x1400178c8  mov     rcx, rbx
0x1400178cb  call    cs:__imp_?GetParentHWND@TaskPage@DirectUI@@QEAAPEAUHWND__@@XZ; DirectUI::TaskPage::GetParentHWND(void)
0x1400178d2  nop     dword ptr [rax+rax+00h]
0x1400178d7  mov     rcx, rax; hWnd
0x1400178da  xor     r9d, r9d; lParam
0x1400178dd  xor     r8d, r8d; wParam
0x1400178e0  mov     edx, 9E8h; Msg
0x1400178e5  call    cs:__imp_PostMessageW
0x1400178ec  nop     dword ptr [rax+rax+00h]
0x1400178f1  nop
0x1400178f2  mov     edx, [rbp+var_8]
0x1400178f5  test    edx, edx
0x1400178f7  jz      short loc_14001790A
0x1400178f9  mov     rcx, [rbp+var_10]
0x1400178fd  call    cs:__imp_?EndDefer@Element@DirectUI@@QEAAXK@Z; DirectUI::Element::EndDefer(ulong)
0x140017904  nop     dword ptr [rax+rax+00h]
0x140017909  nop
0x14001790a  xor     eax, eax
0x14001790c  mov     rbx, [rsp+40h+arg_0]
0x140017911  add     rsp, 40h
0x140017915  pop     rbp
0x140017916  retn
```
