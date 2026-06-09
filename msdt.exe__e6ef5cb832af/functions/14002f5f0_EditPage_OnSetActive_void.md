# EditPage::OnSetActive(void)

- ea: `0x14002f5f0`
- end: `0x14002f886`
- name: `?OnSetActive@EditPage@@MEAA_JXZ`
- size: `662`
- prototype: `__int64 __fastcall(EditPage *__hidden this)`
- caller_count: `0`
- callee_count: `10`
- tags: `service_task`

## callees

- `0x14000e72c`
- `0x14000e978`
- `0x1400108b0`
- `0x140020420`
- `0x140029e80`
- `0x14002a0b8`
- `0x14002d82c`
- `0x14002f5f0`
- `0x14002fc60`
- `0x140063010`

## import_xrefs

- `USER32!ShowScrollBar` at `0x14002f847`
- `USER32!ShowScrollBar` at `0x14002f847`
- `USER32!SendMessageW` at `0x14002f80b`
- `USER32!SendMessageW` at `0x14002f833`
- `USER32!SendMessageW` at `0x14002f80b`
- `USER32!SendMessageW` at `0x14002f833`
- `DUI70!?EndDefer@Element@DirectUI@@QEAAXK@Z` at `0x14002f861`
- `DUI70!?EndDefer@Element@DirectUI@@QEAAXK@Z` at `0x14002f861`
- `DUI70!?GetElement@TaskPage@DirectUI@@IEAAPEAVElement@2@XZ` at `0x14002f60e`
- `DUI70!?GetElement@TaskPage@DirectUI@@IEAAPEAVElement@2@XZ` at `0x14002f60e`
- `DUI70!?StartDefer@Element@DirectUI@@QEAAXPEAK@Z` at `0x14002f62f`
- `DUI70!?StartDefer@Element@DirectUI@@QEAAXPEAK@Z` at `0x14002f62f`
- `DUI70!?PropSheet_SendMessage@TaskPage@DirectUI@@IEAA_JI_K_J@Z` at `0x14002f7dd`
- `DUI70!?PropSheet_SendMessage@TaskPage@DirectUI@@IEAA_JI_K_J@Z` at `0x14002f7dd`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall EditPage::OnSetActive(EditPage *this)
{
  int NamedHandle; // eax
  int v3; // r9d
  const unsigned __int16 *v4; // rsi
  const wchar_t *v5; // rsi
  const wchar_t *v6; // rdx
  HWND v7; // rbx
  DirectUI::Element *Element; // [rsp+30h] [rbp-68h]
  unsigned int v10; // [rsp+38h] [rbp-60h] BYREF
  _BYTE v11[80]; // [rsp+40h] [rbp-58h] BYREF
  HWND hWnd; // [rsp+A0h] [rbp+8h] BYREF

  hWnd = 0;
  Element = DirectUI::TaskPage::GetElement(this);
  v10 = 0;
  DirectUI::Element::StartDefer(Element, &v10);
  InteractivityPage::OnSetActive(this);
  if ( !*((_DWORD *)this + 56) && !*((_DWORD *)this + 58) && !*((_DWORD *)this + 57) )
  {
    if ( (*(unsigned int (__fastcall **)(EditPage *))(*(_QWORD *)this + 264LL))(this) )
    {
      NamedHandle = WizardPage::HideNamedElement(this, L"browse");
      if ( NamedHandle < 0 )
      {
        v3 = 1478;
LABEL_7:
        SdpDebugPrint(1u, "Dwz ERROR: %s:%d - hr = 0x%08X\n", "EditPage::OnSetActive", v3, NamedHandle);
        goto LABEL_31;
      }
    }
  }
  if ( (*(unsigned int (__fastcall **)(EditPage *))(*(_QWORD *)this + 264LL))(this) && *((_DWORD *)this + 56) )
  {
    NamedHandle = WizardPage::HideNamedElement(this, L"edit");
    if ( NamedHandle < 0 )
    {
      v3 = 1485;
      goto LABEL_7;
    }
    NamedHandle = WizardPage::ShowNamedElement(this, L"fileedit", 1);
    if ( NamedHandle < 0 )
    {
      v3 = 1488;
      goto LABEL_7;
    }
    v4 = L"fileedit";
  }
  else
  {
    v4 = L"edit";
    if ( (*(unsigned int (__fastcall **)(EditPage *))(*(_QWORD *)this + 264LL))(this) )
    {
      NamedHandle = WizardPage::HideNamedElement(this, L"fileedit");
      if ( NamedHandle < 0 )
      {
        v3 = 1491;
        goto LABEL_7;
      }
      NamedHandle = WizardPage::ShowNamedElement(this, L"edit", 1);
      if ( NamedHandle < 0 )
      {
        v3 = 1494;
        goto LABEL_7;
      }
    }
  }
  NamedHandle = WizardPage::GetNamedHandle(this, v4, &hWnd);
  if ( NamedHandle < 0 )
  {
    v3 = 1498;
    goto LABEL_7;
  }
  v5 = &word_14006B9B8;
  if ( *((_QWORD *)this + 27) )
  {
    ATL::CAtlREMatchContext<ATL::CAtlRECharTraitsW>::CAtlREMatchContext<ATL::CAtlRECharTraitsW>(v11);
    v6 = &word_14006B9B8;
    if ( *((_QWORD *)this + 24) )
      v6 = (const wchar_t *)*((_QWORD *)this + 24);
    if ( !(unsigned int)ATL::CAtlRegExp<ATL::CAtlRECharTraitsW>::Match(*((_QWORD *)this + 27), v6, v11, 0) )
      DirectUI::TaskPage::PropSheet_SendMessage(this, 0x48Bu, 0, 2);
    ATL::CAtlREMatchContext<ATL::CAtlRECharTraitsW>::~CAtlREMatchContext<ATL::CAtlRECharTraitsW>(v11);
  }
  v7 = hWnd;
  SendMessageW(hWnd, 0xB1u, 0, -1);
  if ( *((_QWORD *)this + 24) )
    v5 = (const wchar_t *)*((_QWORD *)this + 24);
  SendMessageW(v7, 0xC2u, 0, (LPARAM)v5);
  ShowScrollBar(v7, 0, 0);
LABEL_31:
  if ( v10 )
    DirectUI::Element::EndDefer(Element, v10);
  return 0;
}

```

## disassembly

```asm
0x14002f5f0  mov     rax, rsp
0x14002f5f3  mov     [rax+10h], rbx
0x14002f5f7  mov     [rax+18h], rsi
0x14002f5fb  push    rdi
0x14002f5fc  sub     rsp, 90h
0x14002f603  mov     rdi, rcx
0x14002f606  mov     qword ptr [rax+8], 0
0x14002f60e  call    cs:__imp_?GetElement@TaskPage@DirectUI@@IEAAPEAVElement@2@XZ; DirectUI::TaskPage::GetElement(void)
0x14002f615  nop     dword ptr [rax+rax+00h]
0x14002f61a  mov     [rsp+98h+var_68], rax
0x14002f61f  mov     [rsp+98h+var_60], 0
0x14002f627  lea     rdx, [rsp+98h+var_60]
0x14002f62c  mov     rcx, rax
0x14002f62f  call    cs:__imp_?StartDefer@Element@DirectUI@@QEAAXPEAK@Z; DirectUI::Element::StartDefer(ulong *)
0x14002f636  nop     dword ptr [rax+rax+00h]
0x14002f63b  nop
0x14002f63c  mov     rcx, rdi; this
0x14002f63f  call    ?OnSetActive@InteractivityPage@@MEAA_JXZ; InteractivityPage::OnSetActive(void)
0x14002f644  cmp     dword ptr [rdi+0E0h], 0
0x14002f64b  jnz     short loc_14002F6AF
0x14002f64d  cmp     dword ptr [rdi+0E8h], 0
0x14002f654  jnz     short loc_14002F6AF
0x14002f656  cmp     dword ptr [rdi+0E4h], 0
0x14002f65d  jnz     short loc_14002F6AF
0x14002f65f  mov     rax, [rdi]
0x14002f662  mov     rcx, rdi
0x14002f665  mov     rax, [rax+108h]
0x14002f66c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002f671  test    eax, eax
0x14002f673  jz      short loc_14002F6AF
0x14002f675  lea     rdx, aBrowse; "browse"
0x14002f67c  mov     rcx, rdi; this
0x14002f67f  call    ?HideNamedElement@WizardPage@@IEAAJPEBG@Z; WizardPage::HideNamedElement(ushort const *)
0x14002f684  test    eax, eax
0x14002f686  jns     short loc_14002F6AF
0x14002f688  mov     r9d, 5C6h
0x14002f68e  mov     ecx, 1; Level
0x14002f693  mov     [rsp+98h+var_78], eax
0x14002f697  lea     rdx, aDwzErrorSDHr0x; "Dwz ERROR: %s:%d - hr = 0x%08X\n"
0x14002f69e  lea     r8, aEditpageOnseta; "EditPage::OnSetActive"
0x14002f6a5  call    ?SdpDebugPrint@@YAXKPEBDZZ; SdpDebugPrint(ulong,char const *,...)
0x14002f6aa  jmp     loc_14002F854
0x14002f6af  mov     rax, [rdi]
0x14002f6b2  mov     rcx, rdi
0x14002f6b5  mov     rax, [rax+108h]
0x14002f6bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002f6c1  mov     ebx, 1
0x14002f6c6  test    eax, eax
0x14002f6c8  jz      short loc_14002F734
0x14002f6ca  cmp     dword ptr [rdi+0E0h], 0
0x14002f6d1  jz      short loc_14002F734
0x14002f6d3  lea     rdx, ClassName; "edit"
0x14002f6da  mov     rcx, rdi; this
0x14002f6dd  call    ?HideNamedElement@WizardPage@@IEAAJPEBG@Z; WizardPage::HideNamedElement(ushort const *)
0x14002f6e2  test    eax, eax
0x14002f6e4  jns     short loc_14002F6F0
0x14002f6e6  mov     r9d, 5CDh
0x14002f6ec  mov     ecx, ebx
0x14002f6ee  jmp     short loc_14002F693
0x14002f6f0  mov     r8d, ebx; int
0x14002f6f3  lea     rdx, aFileedit; "fileedit"
0x14002f6fa  mov     rcx, rdi; this
0x14002f6fd  call    ?ShowNamedElement@WizardPage@@IEAAJPEBGH@Z; WizardPage::ShowNamedElement(ushort const *,int)
0x14002f702  test    eax, eax
0x14002f704  jns     short loc_14002F70E
0x14002f706  mov     r9d, 5D0h
0x14002f70c  jmp     short loc_14002F6EC
0x14002f70e  lea     rsi, aFileedit; "fileedit"
0x14002f715  lea     r8, [rsp+98h+hWnd]; HWND *
0x14002f71d  mov     rdx, rsi; unsigned __int16 *
0x14002f720  mov     rcx, rdi; this
0x14002f723  call    ?GetNamedHandle@WizardPage@@IEAAJPEBGPEAPEAUHWND__@@@Z; WizardPage::GetNamedHandle(ushort const *,HWND__ * *)
0x14002f728  test    eax, eax
0x14002f72a  jns     short loc_14002F789
0x14002f72c  mov     r9d, 5DAh
0x14002f732  jmp     short loc_14002F6EC
0x14002f734  lea     rsi, ClassName; "edit"
0x14002f73b  mov     rax, [rdi]
0x14002f73e  mov     rcx, rdi
0x14002f741  mov     rax, [rax+108h]
0x14002f748  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002f74d  test    eax, eax
0x14002f74f  jz      short loc_14002F715
0x14002f751  lea     rdx, aFileedit; "fileedit"
0x14002f758  mov     rcx, rdi; this
0x14002f75b  call    ?HideNamedElement@WizardPage@@IEAAJPEBG@Z; WizardPage::HideNamedElement(ushort const *)
0x14002f760  test    eax, eax
0x14002f762  jns     short loc_14002F76C
0x14002f764  mov     r9d, 5D3h
0x14002f76a  jmp     short loc_14002F6EC
0x14002f76c  mov     r8d, ebx; int
0x14002f76f  mov     rdx, rsi; unsigned __int16 *
0x14002f772  mov     rcx, rdi; this
0x14002f775  call    ?ShowNamedElement@WizardPage@@IEAAJPEBGH@Z; WizardPage::ShowNamedElement(ushort const *,int)
0x14002f77a  test    eax, eax
0x14002f77c  jns     short loc_14002F715
0x14002f77e  mov     r9d, 5D6h
0x14002f784  jmp     loc_14002F6EC
0x14002f789  lea     rsi, word_14006B9B8
0x14002f790  cmp     qword ptr [rdi+0D8h], 0
0x14002f798  jz      short loc_14002F7F4
0x14002f79a  lea     rcx, [rsp+98h+var_58]
0x14002f79f  call    ??0?$CAtlREMatchContext@VCAtlRECharTraitsW@ATL@@@ATL@@QEAA@_K@Z; ATL::CAtlREMatchContext<ATL::CAtlRECharTraitsW>::CAtlREMatchContext<ATL::CAtlRECharTraitsW>(unsigned __int64)
0x14002f7a4  nop
0x14002f7a5  mov     rax, [rdi+0C0h]
0x14002f7ac  mov     rdx, rsi
0x14002f7af  test    rax, rax
0x14002f7b2  cmovnz  rdx, rax
0x14002f7b6  xor     r9d, r9d
0x14002f7b9  lea     r8, [rsp+98h+var_58]
0x14002f7be  mov     rcx, [rdi+0D8h]
0x14002f7c5  call    ?Match@?$CAtlRegExp@VCAtlRECharTraitsW@ATL@@@ATL@@QEAAHPEBGPEAV?$CAtlREMatchContext@VCAtlRECharTraitsW@ATL@@@2@PEAPEBG@Z; ATL::CAtlRegExp<ATL::CAtlRECharTraitsW>::Match(ushort const *,ATL::CAtlREMatchContext<ATL::CAtlRECharTraitsW> *,ushort const * *)
0x14002f7ca  test    eax, eax
0x14002f7cc  jnz     short loc_14002F7EA
0x14002f7ce  lea     r9d, [rax+2]
0x14002f7d2  xor     r8d, r8d
0x14002f7d5  mov     edx, 48Bh
0x14002f7da  mov     rcx, rdi
0x14002f7dd  call    cs:__imp_?PropSheet_SendMessage@TaskPage@DirectUI@@IEAA_JI_K_J@Z; DirectUI::TaskPage::PropSheet_SendMessage(uint,unsigned __int64,__int64)
0x14002f7e4  nop     dword ptr [rax+rax+00h]
0x14002f7e9  nop
0x14002f7ea  lea     rcx, [rsp+98h+var_58]
0x14002f7ef  call    ??1?$CAtlREMatchContext@VCAtlRECharTraitsW@ATL@@@ATL@@QEAA@XZ; ATL::CAtlREMatchContext<ATL::CAtlRECharTraitsW>::~CAtlREMatchContext<ATL::CAtlRECharTraitsW>(void)
0x14002f7f4  or      r9, 0FFFFFFFFFFFFFFFFh; lParam
0x14002f7f8  xor     r8d, r8d; wParam
0x14002f7fb  mov     edx, 0B1h; Msg
0x14002f800  mov     rbx, [rsp+98h+hWnd]
0x14002f808  mov     rcx, rbx; hWnd
0x14002f80b  call    cs:__imp_SendMessageW
0x14002f812  nop     dword ptr [rax+rax+00h]
0x14002f817  mov     rax, [rdi+0C0h]
0x14002f81e  test    rax, rax
0x14002f821  cmovnz  rsi, rax
0x14002f825  mov     r9, rsi; lParam
0x14002f828  xor     r8d, r8d; wParam
0x14002f82b  mov     edx, 0C2h; Msg
0x14002f830  mov     rcx, rbx; hWnd
0x14002f833  call    cs:__imp_SendMessageW
0x14002f83a  nop     dword ptr [rax+rax+00h]
0x14002f83f  xor     r8d, r8d; bShow
0x14002f842  xor     edx, edx; wBar
0x14002f844  mov     rcx, rbx; hWnd
0x14002f847  call    cs:__imp_ShowScrollBar
0x14002f84e  nop     dword ptr [rax+rax+00h]
0x14002f853  nop
0x14002f854  mov     edx, [rsp+98h+var_60]
0x14002f858  test    edx, edx
0x14002f85a  jz      short loc_14002F86E
0x14002f85c  mov     rcx, [rsp+98h+var_68]
0x14002f861  call    cs:__imp_?EndDefer@Element@DirectUI@@QEAAXK@Z; DirectUI::Element::EndDefer(ulong)
0x14002f868  nop     dword ptr [rax+rax+00h]
0x14002f86d  nop
0x14002f86e  xor     eax, eax
0x14002f870  lea     r11, [rsp+98h+var_8]
0x14002f878  mov     rbx, [r11+18h]
0x14002f87c  mov     rsi, [r11+20h]
0x14002f880  mov     rsp, r11
0x14002f883  pop     rdi
0x14002f884  retn
```
