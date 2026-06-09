# EulaPage::OnSetActive(void)

- ea: `0x14002f890`
- end: `0x14002fc54`
- name: `?OnSetActive@EulaPage@@MEAA_JXZ`
- size: `964`
- prototype: `__int64 __fastcall(EulaPage *__hidden this)`
- caller_count: `0`
- callee_count: `12`
- tags: `service_task`

## callees

- `0x14000e6bc`
- `0x14000e72c`
- `0x14000e978`
- `0x14000f480`
- `0x1400104bc`
- `0x1400108b0`
- `0x140010a10`
- `0x140020420`
- `0x14002d40c`
- `0x14002f890`
- `0x140041c54`
- `0x140063010`

## import_xrefs

- `KERNEL32!HeapAlloc` at `0x14002f8df`
- `KERNEL32!HeapAlloc` at `0x14002f8df`
- `KERNEL32!HeapFree` at `0x14002fc1f`
- `KERNEL32!HeapFree` at `0x14002fc1f`
- `KERNEL32!GetProcessHeap` at `0x14002f8c8`
- `KERNEL32!GetProcessHeap` at `0x14002fc0b`
- `KERNEL32!GetProcessHeap` at `0x14002f8c8`
- `KERNEL32!GetProcessHeap` at `0x14002fc0b`
- `USER32!ShowScrollBar` at `0x14002fbbc`
- `USER32!ShowScrollBar` at `0x14002fbbc`
- `USER32!PostMessageW` at `0x14002fa32`
- `USER32!PostMessageW` at `0x14002fa32`
- `USER32!SendMessageW` at `0x14002fb8d`
- `USER32!SendMessageW` at `0x14002fba8`
- `USER32!SendMessageW` at `0x14002fb8d`
- `USER32!SendMessageW` at `0x14002fba8`
- `DUI70!?SetContentString@Element@DirectUI@@QEAAJPEBG@Z` at `0x14002fb5f`
- `DUI70!?SetContentString@Element@DirectUI@@QEAAJPEBG@Z` at `0x14002fb5f`
- `DUI70!StrToID` at `0x14002fafd`
- `DUI70!StrToID` at `0x14002fafd`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x14002fb0f`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x14002fb0f`
- `DUI70!?EndDefer@Element@DirectUI@@QEAAXK@Z` at `0x14002fa4a`
- `DUI70!?EndDefer@Element@DirectUI@@QEAAXK@Z` at `0x14002fc37`
- `DUI70!?EndDefer@Element@DirectUI@@QEAAXK@Z` at `0x14002fa4a`
- `DUI70!?EndDefer@Element@DirectUI@@QEAAXK@Z` at `0x14002fc37`
- `DUI70!?StartDefer@Element@DirectUI@@QEAAXPEAK@Z` at `0x14002f8bb`
- `DUI70!?StartDefer@Element@DirectUI@@QEAAXPEAK@Z` at `0x14002f8bb`
- `DUI70!?PropSheet_SendMessage@TaskPage@DirectUI@@IEAA_JI_K_J@Z` at `0x14002fbff`
- `DUI70!?PropSheet_SendMessage@TaskPage@DirectUI@@IEAA_JI_K_J@Z` at `0x14002fbff`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall EulaPage::OnSetActive(EulaPage *this)
{
  HANDLE ProcessHeap; // rax
  WCHAR *v3; // rsi
  int LocalString; // eax
  int v5; // r9d
  HWND v6; // rbx
  int RTF; // eax
  DirectUI::Element *v9; // rbx
  unsigned __int16 v10; // ax
  DirectUI::Element *Descendent; // rbx
  HANDLE v12; // rax
  DirectUI::Element *v13; // [rsp+30h] [rbp-10h]
  unsigned int v14; // [rsp+38h] [rbp-8h] BYREF
  HWND hWnd; // [rsp+60h] [rbp+20h] BYREF
  struct DirectUI::Element *v16; // [rsp+68h] [rbp+28h] BYREF

  hWnd = 0;
  v16 = 0;
  v13 = (DirectUI::Element *)*((_QWORD *)this + 8);
  v14 = 0;
  DirectUI::Element::StartDefer(v13, &v14);
  ProcessHeap = GetProcessHeap();
  v3 = (WCHAR *)HeapAlloc(ProcessHeap, 0, 0x200u);
  if ( !v3 )
  {
    SdpDebugPrint(1u, "Dwz ERROR: %s:%d - hr = 0x%08X\n", "EulaPage::OnSetActive", 3038, -2147024882);
LABEL_40:
    if ( v14 )
      DirectUI::Element::EndDefer(v13, v14);
    return 0;
  }
  WizardPage::StartRetireBannerTipTest(this, 5);
  WizardPage::OnSetActive(this);
  LocalString = WizardPage::HideNamedElement(this, L"rtf");
  if ( LocalString < 0 )
  {
    v5 = 3052;
LABEL_5:
    SdpDebugPrint(1u, "Dwz ERROR: %s:%d - hr = 0x%08X\n", "EulaPage::OnSetActive", v5, LocalString);
    goto LABEL_39;
  }
  LocalString = DwzLoadLocalString(0x153u, v3, 0x100u);
  if ( LocalString < 0 )
  {
    v5 = 3055;
    goto LABEL_5;
  }
  LocalString = WizardPage::SetHeader(this, v3);
  if ( LocalString < 0 )
  {
    v5 = 3061;
    goto LABEL_5;
  }
  LocalString = WizardPage::HideNamedElement(this, L"txtDescription");
  if ( LocalString < 0 )
  {
    v5 = 3064;
    goto LABEL_5;
  }
  LocalString = WizardPage::HideNamedElement(this, L"interactionHeader");
  if ( LocalString < 0 )
  {
    v5 = 3070;
    goto LABEL_5;
  }
  if ( !*((_QWORD *)this + 18) )
    goto LABEL_27;
  LocalString = WizardPage::GetNamedHandle(this, L"editRichEula", &hWnd);
  if ( LocalString < 0 )
  {
    v5 = 3078;
    goto LABEL_5;
  }
  v6 = hWnd;
  RTF = InteractivityPage::LoadRTF(this, hWnd, *((const unsigned __int16 **)this + 18));
  if ( RTF >= 0 )
  {
    if ( *((_QWORD *)this + 18) )
    {
      LocalString = WizardPage::HideNamedElement(this, L"edit");
      if ( LocalString < 0 )
      {
        v5 = 3092;
        goto LABEL_5;
      }
      LocalString = WizardPage::ShowNamedElement(this, L"editRichEula", 4);
      if ( LocalString < 0 )
      {
        v5 = 3095;
        goto LABEL_5;
      }
      goto LABEL_38;
    }
LABEL_27:
    LocalString = WizardPage::HideNamedElement(this, L"editRichEula");
    if ( LocalString < 0 )
    {
      v5 = 3098;
      goto LABEL_5;
    }
    LocalString = WizardPage::ShowNamedElement(this, L"edit", 4);
    if ( LocalString < 0 )
    {
      v5 = 3101;
      goto LABEL_5;
    }
    v9 = (DirectUI::Element *)*((_QWORD *)this + 8);
    v10 = StrToID(L"edit");
    Descendent = DirectUI::Element::FindDescendent(v9, v10);
    if ( !Descendent )
    {
      SdpDebugPrint(1u, "Dwz ERROR: %s:%d - hr = 0x%08X\n", "EulaPage::OnSetActive", 3104, -2147418113);
LABEL_39:
      v12 = GetProcessHeap();
      HeapFree(v12, 0, v3);
      goto LABEL_40;
    }
    LocalString = WizardPage::GetNamedHandle(this, L"edit", &hWnd);
    if ( LocalString < 0 )
    {
      v5 = 3107;
      goto LABEL_5;
    }
    LocalString = DirectUI::Element::SetContentString(Descendent, *((const unsigned __int16 **)this + 15));
    if ( LocalString < 0 )
    {
      v5 = 3110;
      goto LABEL_5;
    }
    v6 = hWnd;
LABEL_38:
    SendMessageW(v6, 0xB1u, 0xFFFFFFFFFFFFFFFFuLL, 0);
    SendMessageW(v6, 0xCFu, 1u, 0);
    ShowScrollBar(v6, 0, 0);
    WizardPage::GetNamedElement(this, L"cbEula", &v16);
    (*(void (__fastcall **)(struct DirectUI::Element *))(*(_QWORD *)v16 + 168LL))(v16);
    DirectUI::TaskPage::PropSheet_SendMessage(this, 0x48Bu, 0, 2);
    goto LABEL_39;
  }
  PostMessageW(*((HWND *)this + 7), 0x9E2u, 0, RTF);
  if ( v14 )
    DirectUI::Element::EndDefer(v13, v14);
  return -1;
}

```

## disassembly

```asm
0x14002f890  mov     [rsp-18h+arg_10], rbx
0x14002f895  push    rbp
0x14002f896  push    rsi
0x14002f897  push    rdi
0x14002f898  mov     rbp, rsp
0x14002f89b  sub     rsp, 40h
0x14002f89f  mov     rdi, rcx
0x14002f8a2  xor     ebx, ebx
0x14002f8a4  mov     [rbp+hWnd], rbx
0x14002f8a8  mov     [rbp+arg_8], rbx
0x14002f8ac  mov     rcx, [rcx+40h]
0x14002f8b0  mov     [rbp+var_10], rcx
0x14002f8b4  mov     [rbp+var_8], ebx
0x14002f8b7  lea     rdx, [rbp+var_8]
0x14002f8bb  call    cs:__imp_?StartDefer@Element@DirectUI@@QEAAXPEAK@Z; DirectUI::Element::StartDefer(ulong *)
0x14002f8c2  nop     dword ptr [rax+rax+00h]
0x14002f8c7  nop
0x14002f8c8  call    cs:__imp_GetProcessHeap
0x14002f8cf  nop     dword ptr [rax+rax+00h]
0x14002f8d4  mov     rcx, rax; hHeap
0x14002f8d7  xor     edx, edx; dwFlags
0x14002f8d9  mov     r8d, 200h; dwBytes
0x14002f8df  call    cs:__imp_HeapAlloc
0x14002f8e6  nop     dword ptr [rax+rax+00h]
0x14002f8eb  mov     rsi, rax
0x14002f8ee  test    rax, rax
0x14002f8f1  jnz     short loc_14002F91C
0x14002f8f3  mov     [rsp+40h+var_20], 8007000Eh
0x14002f8fb  mov     r9d, 0BDEh
0x14002f901  lea     r8, aEulapageOnseta; "EulaPage::OnSetActive"
0x14002f908  lea     rdx, aDwzErrorSDHr0x; "Dwz ERROR: %s:%d - hr = 0x%08X\n"
0x14002f90f  lea     ecx, [rbx+1]; Level
0x14002f912  call    ?SdpDebugPrint@@YAXKPEBDZZ; SdpDebugPrint(ulong,char const *,...)
0x14002f917  jmp     loc_14002FC2C
0x14002f91c  mov     edx, 5
0x14002f921  mov     rcx, rdi
0x14002f924  call    ?StartRetireBannerTipTest@WizardPage@@IEAAXW4PageNames@@@Z; WizardPage::StartRetireBannerTipTest(PageNames)
0x14002f929  mov     rcx, rdi; this
0x14002f92c  call    ?OnSetActive@WizardPage@@MEAA_JXZ; WizardPage::OnSetActive(void)
0x14002f931  lea     rdx, aRtf; "rtf"
0x14002f938  mov     rcx, rdi; this
0x14002f93b  call    ?HideNamedElement@WizardPage@@IEAAJPEBG@Z; WizardPage::HideNamedElement(ushort const *)
0x14002f940  test    eax, eax
0x14002f942  jns     short loc_14002F96B
0x14002f944  mov     r9d, 0BECh
0x14002f94a  mov     [rsp+40h+var_20], eax
0x14002f94e  lea     r8, aEulapageOnseta; "EulaPage::OnSetActive"
0x14002f955  lea     rdx, aDwzErrorSDHr0x; "Dwz ERROR: %s:%d - hr = 0x%08X\n"
0x14002f95c  mov     ecx, 1; Level
0x14002f961  call    ?SdpDebugPrint@@YAXKPEBDZZ; SdpDebugPrint(ulong,char const *,...)
0x14002f966  jmp     loc_14002FC0B
0x14002f96b  mov     r8d, 100h; cchBufferMax
0x14002f971  mov     rdx, rsi; lpBuffer
0x14002f974  lea     ecx, [r8+53h]; uID
0x14002f978  call    ?DwzLoadLocalString@@YAJIPEAG_K@Z; DwzLoadLocalString(uint,ushort *,unsigned __int64)
0x14002f97d  test    eax, eax
0x14002f97f  jns     short loc_14002F989
0x14002f981  mov     r9d, 0BEFh
0x14002f987  jmp     short loc_14002F94A
0x14002f989  mov     rdx, rsi; unsigned __int16 *
0x14002f98c  mov     rcx, rdi; this
0x14002f98f  call    ?SetHeader@WizardPage@@IEAAJPEBG@Z; WizardPage::SetHeader(ushort const *)
0x14002f994  test    eax, eax
0x14002f996  jns     short loc_14002F9A0
0x14002f998  mov     r9d, 0BF5h
0x14002f99e  jmp     short loc_14002F94A
0x14002f9a0  lea     rdx, aTxtdescription; "txtDescription"
0x14002f9a7  mov     rcx, rdi; this
0x14002f9aa  call    ?HideNamedElement@WizardPage@@IEAAJPEBG@Z; WizardPage::HideNamedElement(ushort const *)
0x14002f9af  test    eax, eax
0x14002f9b1  jns     short loc_14002F9BB
0x14002f9b3  mov     r9d, 0BF8h
0x14002f9b9  jmp     short loc_14002F94A
0x14002f9bb  lea     rdx, aInteractionhea; "interactionHeader"
0x14002f9c2  mov     rcx, rdi; this
0x14002f9c5  call    ?HideNamedElement@WizardPage@@IEAAJPEBG@Z; WizardPage::HideNamedElement(ushort const *)
0x14002f9ca  test    eax, eax
0x14002f9cc  jns     short loc_14002F9D9
0x14002f9ce  mov     r9d, 0BFEh
0x14002f9d4  jmp     loc_14002F94A
0x14002f9d9  cmp     qword ptr [rdi+90h], 0
0x14002f9e1  jz      loc_14002FAB0
0x14002f9e7  lea     r8, [rbp+hWnd]; HWND *
0x14002f9eb  lea     rdx, aEditricheula; "editRichEula"
0x14002f9f2  mov     rcx, rdi; this
0x14002f9f5  call    ?GetNamedHandle@WizardPage@@IEAAJPEBGPEAPEAUHWND__@@@Z; WizardPage::GetNamedHandle(ushort const *,HWND__ * *)
0x14002f9fa  test    eax, eax
0x14002f9fc  jns     short loc_14002FA09
0x14002f9fe  mov     r9d, 0C06h
0x14002fa04  jmp     loc_14002F94A
0x14002fa09  mov     r8, [rdi+90h]; unsigned __int16 *
0x14002fa10  mov     rbx, [rbp+hWnd]
0x14002fa14  mov     rdx, rbx; HWND
0x14002fa17  mov     rcx, rdi; this
0x14002fa1a  call    ?LoadRTF@InteractivityPage@@IEAAJPEAUHWND__@@PEBG@Z; InteractivityPage::LoadRTF(HWND__ *,ushort const *)
0x14002fa1f  test    eax, eax
0x14002fa21  jns     short loc_14002FA60
0x14002fa23  movsxd  r9, eax; lParam
0x14002fa26  xor     r8d, r8d; wParam
0x14002fa29  mov     edx, 9E2h; Msg
0x14002fa2e  mov     rcx, [rdi+38h]; hWnd
0x14002fa32  call    cs:__imp_PostMessageW
0x14002fa39  nop     dword ptr [rax+rax+00h]
0x14002fa3e  nop
0x14002fa3f  mov     edx, [rbp+var_8]
0x14002fa42  test    edx, edx
0x14002fa44  jz      short loc_14002FA57
0x14002fa46  mov     rcx, [rbp+var_10]
0x14002fa4a  call    cs:__imp_?EndDefer@Element@DirectUI@@QEAAXK@Z; DirectUI::Element::EndDefer(ulong)
0x14002fa51  nop     dword ptr [rax+rax+00h]
0x14002fa56  nop
0x14002fa57  or      rax, 0FFFFFFFFFFFFFFFFh
0x14002fa5b  jmp     loc_14002FC46
0x14002fa60  cmp     qword ptr [rdi+90h], 0
0x14002fa68  jz      short loc_14002FAB0
0x14002fa6a  lea     rdx, ClassName; "edit"
0x14002fa71  mov     rcx, rdi; this
0x14002fa74  call    ?HideNamedElement@WizardPage@@IEAAJPEBG@Z; WizardPage::HideNamedElement(ushort const *)
0x14002fa79  test    eax, eax
0x14002fa7b  jns     short loc_14002FA88
0x14002fa7d  mov     r9d, 0C14h
0x14002fa83  jmp     loc_14002F94A
0x14002fa88  mov     r8d, 4; int
0x14002fa8e  lea     rdx, aEditricheula; "editRichEula"
0x14002fa95  mov     rcx, rdi; this
0x14002fa98  call    ?ShowNamedElement@WizardPage@@IEAAJPEBGH@Z; WizardPage::ShowNamedElement(ushort const *,int)
0x14002fa9d  test    eax, eax
0x14002fa9f  jns     loc_14002FB7E
0x14002faa5  mov     r9d, 0C17h
0x14002faab  jmp     loc_14002F94A
0x14002fab0  lea     rdx, aEditricheula; "editRichEula"
0x14002fab7  mov     rcx, rdi; this
0x14002faba  call    ?HideNamedElement@WizardPage@@IEAAJPEBG@Z; WizardPage::HideNamedElement(ushort const *)
0x14002fabf  test    eax, eax
0x14002fac1  jns     short loc_14002FACE
0x14002fac3  mov     r9d, 0C1Ah
0x14002fac9  jmp     loc_14002F94A
0x14002face  mov     r8d, 4; int
0x14002fad4  lea     rdx, ClassName; "edit"
0x14002fadb  mov     rcx, rdi; this
0x14002fade  call    ?ShowNamedElement@WizardPage@@IEAAJPEBGH@Z; WizardPage::ShowNamedElement(ushort const *,int)
0x14002fae3  test    eax, eax
0x14002fae5  jns     short loc_14002FAF2
0x14002fae7  mov     r9d, 0C1Dh
0x14002faed  jmp     loc_14002F94A
0x14002faf2  mov     rbx, [rdi+40h]
0x14002faf6  lea     rcx, ClassName; "edit"
0x14002fafd  call    cs:__imp_StrToID
0x14002fb04  nop     dword ptr [rax+rax+00h]
0x14002fb09  movzx   edx, ax
0x14002fb0c  mov     rcx, rbx
0x14002fb0f  call    cs:__imp_?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z; DirectUI::Element::FindDescendent(ushort)
0x14002fb16  nop     dword ptr [rax+rax+00h]
0x14002fb1b  mov     rbx, rax
0x14002fb1e  test    rax, rax
0x14002fb21  jnz     short loc_14002FB36
0x14002fb23  mov     [rsp+40h+var_20], 8000FFFFh
0x14002fb2b  mov     r9d, 0C20h
0x14002fb31  jmp     loc_14002F94E
0x14002fb36  lea     r8, [rbp+hWnd]; HWND *
0x14002fb3a  lea     rdx, ClassName; "edit"
0x14002fb41  mov     rcx, rdi; this
0x14002fb44  call    ?GetNamedHandle@WizardPage@@IEAAJPEBGPEAPEAUHWND__@@@Z; WizardPage::GetNamedHandle(ushort const *,HWND__ * *)
0x14002fb49  test    eax, eax
0x14002fb4b  jns     short loc_14002FB58
0x14002fb4d  mov     r9d, 0C23h
0x14002fb53  jmp     loc_14002F94A
0x14002fb58  mov     rdx, [rdi+78h]
0x14002fb5c  mov     rcx, rbx
0x14002fb5f  call    cs:__imp_?SetContentString@Element@DirectUI@@QEAAJPEBG@Z; DirectUI::Element::SetContentString(ushort const *)
0x14002fb66  nop     dword ptr [rax+rax+00h]
0x14002fb6b  test    eax, eax
0x14002fb6d  jns     short loc_14002FB7A
0x14002fb6f  mov     r9d, 0C26h
0x14002fb75  jmp     loc_14002F94A
0x14002fb7a  mov     rbx, [rbp+hWnd]
0x14002fb7e  xor     r9d, r9d; lParam
0x14002fb81  or      r8, 0FFFFFFFFFFFFFFFFh; wParam
0x14002fb85  mov     edx, 0B1h; Msg
0x14002fb8a  mov     rcx, rbx; hWnd
0x14002fb8d  call    cs:__imp_SendMessageW
0x14002fb94  nop     dword ptr [rax+rax+00h]
0x14002fb99  xor     r9d, r9d; lParam
0x14002fb9c  mov     edx, 0CFh; Msg
0x14002fba1  lea     r8d, [r9+1]; wParam
0x14002fba5  mov     rcx, rbx; hWnd
0x14002fba8  call    cs:__imp_SendMessageW
0x14002fbaf  nop     dword ptr [rax+rax+00h]
0x14002fbb4  xor     r8d, r8d; bShow
0x14002fbb7  xor     edx, edx; wBar
0x14002fbb9  mov     rcx, rbx; hWnd
0x14002fbbc  call    cs:__imp_ShowScrollBar
0x14002fbc3  nop     dword ptr [rax+rax+00h]
0x14002fbc8  lea     r8, [rbp+arg_8]; struct DirectUI::Element **
0x14002fbcc  lea     rdx, aCbeula; "cbEula"
0x14002fbd3  mov     rcx, rdi; this
0x14002fbd6  call    ?GetNamedElement@WizardPage@@QEAAJPEBGPEAPEAVElement@DirectUI@@@Z; WizardPage::GetNamedElement(ushort const *,DirectUI::Element * *)
0x14002fbdb  mov     rcx, [rbp+arg_8]
0x14002fbdf  mov     rax, [rcx]
0x14002fbe2  mov     rax, [rax+0A8h]
0x14002fbe9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002fbee  mov     r9d, 2
0x14002fbf4  xor     r8d, r8d
0x14002fbf7  mov     edx, 48Bh
0x14002fbfc  mov     rcx, rdi
0x14002fbff  call    cs:__imp_?PropSheet_SendMessage@TaskPage@DirectUI@@IEAA_JI_K_J@Z; DirectUI::TaskPage::PropSheet_SendMessage(uint,unsigned __int64,__int64)
0x14002fc06  nop     dword ptr [rax+rax+00h]
0x14002fc0b  call    cs:__imp_GetProcessHeap
0x14002fc12  nop     dword ptr [rax+rax+00h]
0x14002fc17  mov     rcx, rax; hHeap
0x14002fc1a  mov     r8, rsi; lpMem
0x14002fc1d  xor     edx, edx; dwFlags
0x14002fc1f  call    cs:__imp_HeapFree
0x14002fc26  nop     dword ptr [rax+rax+00h]
0x14002fc2b  nop
0x14002fc2c  mov     edx, [rbp+var_8]
0x14002fc2f  test    edx, edx
0x14002fc31  jz      short loc_14002FC44
0x14002fc33  mov     rcx, [rbp+var_10]
0x14002fc37  call    cs:__imp_?EndDefer@Element@DirectUI@@QEAAXK@Z; DirectUI::Element::EndDefer(ulong)
0x14002fc3e  nop     dword ptr [rax+rax+00h]
0x14002fc43  nop
0x14002fc44  xor     eax, eax
0x14002fc46  mov     rbx, [rsp+40h+arg_10]
0x14002fc4b  add     rsp, 40h
0x14002fc4f  pop     rdi
0x14002fc50  pop     rsi
0x14002fc51  pop     rbp
0x14002fc52  retn
```
