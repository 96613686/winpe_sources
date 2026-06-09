# CheckBoxPage::OnSetActive(void)

- ea: `0x14002eed0`
- end: `0x14002f267`
- name: `?OnSetActive@CheckBoxPage@@MEAA_JXZ`
- size: `919`
- prototype: `__int64 __fastcall(CheckBoxPage *__hidden this)`
- caller_count: `0`
- callee_count: `14`
- tags: `service_task`

## callees

- `0x14000706c`
- `0x1400070b0`
- `0x14000e300`
- `0x14000e72c`
- `0x14000e978`
- `0x140010680`
- `0x1400108b0`
- `0x140020420`
- `0x140020d58`
- `0x14002ad30`
- `0x14002d660`
- `0x14002eed0`
- `0x14002fc60`
- `0x140061c90`

## import_xrefs

- `KERNEL32!HeapAlloc` at `0x14002ef4e`
- `KERNEL32!HeapAlloc` at `0x14002efa2`
- `KERNEL32!HeapAlloc` at `0x14002ef4e`
- `KERNEL32!HeapAlloc` at `0x14002efa2`
- `KERNEL32!HeapFree` at `0x14002f1fd`
- `KERNEL32!HeapFree` at `0x14002f222`
- `KERNEL32!HeapFree` at `0x14002f1fd`
- `KERNEL32!HeapFree` at `0x14002f222`
- `KERNEL32!GetProcessHeap` at `0x14002ef37`
- `KERNEL32!GetProcessHeap` at `0x14002ef8b`
- `KERNEL32!GetProcessHeap` at `0x14002f1e9`
- `KERNEL32!GetProcessHeap` at `0x14002f20e`
- `KERNEL32!GetProcessHeap` at `0x14002ef37`
- `KERNEL32!GetProcessHeap` at `0x14002ef8b`
- `KERNEL32!GetProcessHeap` at `0x14002f1e9`
- `KERNEL32!GetProcessHeap` at `0x14002f20e`
- `USER32!PostMessageW` at `0x14002f111`
- `USER32!PostMessageW` at `0x14002f111`
- `DUI70!?EndDefer@Element@DirectUI@@QEAAXK@Z` at `0x14002f23a`
- `DUI70!?EndDefer@Element@DirectUI@@QEAAXK@Z` at `0x14002f23a`
- `DUI70!?GetElement@TaskPage@DirectUI@@IEAAPEAVElement@2@XZ` at `0x14002ef0c`
- `DUI70!?GetElement@TaskPage@DirectUI@@IEAAPEAVElement@2@XZ` at `0x14002ef0c`
- `DUI70!?StartDefer@Element@DirectUI@@QEAAXPEAK@Z` at `0x14002ef2a`
- `DUI70!?StartDefer@Element@DirectUI@@QEAAXPEAK@Z` at `0x14002ef2a`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CheckBoxPage::OnSetActive(CheckBoxPage *this)
{
  HANDLE ProcessHeap; // rax
  unsigned __int16 *v3; // r13
  HANDLE v4; // rax
  unsigned __int16 *v5; // r12
  unsigned int i; // r15d
  unsigned int v7; // r14d
  int Item; // eax
  struct InteractivityChoice *v9; // r14
  int v10; // r9d
  int ButtonImageList; // eax
  HANDLE v12; // rax
  HANDLE v13; // rax
  const unsigned __int16 *v15; // [rsp+20h] [rbp-58h]
  int v16; // [rsp+30h] [rbp-48h] BYREF
  unsigned int v17; // [rsp+34h] [rbp-44h]
  HWND hWnd; // [rsp+38h] [rbp-40h] BYREF
  struct InteractivityChoice *v19; // [rsp+40h] [rbp-38h] BYREF
  DirectUI::Element *Element; // [rsp+48h] [rbp-30h]
  unsigned int v21; // [rsp+50h] [rbp-28h] BYREF
  unsigned __int16 v22; // [rsp+58h] [rbp-20h] BYREF

  v19 = 0;
  v16 = 0;
  hWnd = 0;
  Element = DirectUI::TaskPage::GetElement(this);
  v21 = 0;
  DirectUI::Element::StartDefer(Element, &v21);
  ProcessHeap = GetProcessHeap();
  v3 = (unsigned __int16 *)HeapAlloc(ProcessHeap, 0, 0x1800u);
  if ( v3 )
  {
    v4 = GetProcessHeap();
    v5 = (unsigned __int16 *)HeapAlloc(v4, 0, 0x200u);
    if ( v5 )
    {
      InteractivityPage::OnSetActive(this);
      for ( i = 0; ; i = v17 )
      {
        v7 = *((_DWORD *)this + 42);
        if ( i >= v7 )
          break;
        v17 = i + 1;
        Item = StringCchPrintfW(&v22, 4u, L"cb%d", i + 1);
        if ( Item < 0 )
        {
          v10 = 2675;
          goto LABEL_34;
        }
        Item = InteractivityPage::GetItem(this, i, &v19);
        if ( Item < 0 )
        {
          v10 = 2678;
          goto LABEL_34;
        }
        v9 = v19;
        Item = DwzStrTruncate(v5, 0x100u, *(const unsigned __int16 **)v19, &v16);
        if ( Item < 0 )
        {
          v10 = 2685;
          goto LABEL_34;
        }
        if ( v16 )
        {
          v15 = (const unsigned __int16 *)*((_QWORD *)v9 + 1);
          Item = StringCchPrintfW(v3, 0xC00u, L"%s\n\n%s", *(_QWORD *)v9);
          if ( Item < 0 )
          {
            v10 = 2698;
LABEL_34:
            SdpDebugPrint(1u, "Dwz ERROR: %s:%d - hr = 0x%08X\n", "CheckBoxPage::OnSetActive", v10, Item);
            goto LABEL_35;
          }
        }
        else
        {
          Item = StringCchCopyW(v3, 0xC00u, *((const unsigned __int16 **)v9 + 1));
          if ( Item < 0 )
          {
            v10 = 2704;
            goto LABEL_34;
          }
        }
        Item = WizardPage::SetNamedValues(this, &v22, v5, *(const unsigned __int16 **)v9, v15, v3);
        if ( Item < 0 )
        {
          v10 = 2713;
          goto LABEL_34;
        }
        Item = WizardPage::ShowNamedElement(this, &v22, 1);
        if ( Item < 0 )
        {
          v10 = 2716;
          goto LABEL_34;
        }
        Item = WizardPage::EnableNamedTooltip(this, &v22, 1);
        if ( Item < 0 )
        {
          v10 = 2719;
          goto LABEL_34;
        }
        Item = WizardPage::GetNamedHandle(this, &v22, &hWnd);
        if ( Item < 0 )
        {
          v10 = 2722;
          goto LABEL_34;
        }
        PostMessageW(hWnd, 0xF1u, *((_DWORD *)v9 + 10) != 0, 0);
        ButtonImageList = InteractivityChoice::MakeButtonImageList(v9, hWnd);
        if ( ButtonImageList < 0 )
          SdpDebugPrint(1u, "Dwz WARNING: %s:%d - hr = 0x%08X\n", "CheckBoxPage::OnSetActive", 2731, ButtonImageList);
      }
      while ( v7 < 4 )
      {
        Item = StringCchPrintfW(&v22, 4u, L"cb%d", ++v7);
        if ( Item < 0 )
        {
          v10 = 2739;
          goto LABEL_34;
        }
        Item = WizardPage::HideNamedElement(this, &v22);
        if ( Item < 0 )
        {
          v10 = 2742;
          goto LABEL_34;
        }
      }
    }
    else
    {
      SdpDebugPrint(1u, "Dwz ERROR: %s:%d - hr = 0x%08X\n", "CheckBoxPage::OnSetActive", 2666, -2147024882);
    }
LABEL_35:
    v12 = GetProcessHeap();
    HeapFree(v12, 0, v3);
    if ( v5 )
    {
      v13 = GetProcessHeap();
      HeapFree(v13, 0, v5);
    }
  }
  else
  {
    SdpDebugPrint(1u, "Dwz ERROR: %s:%d - hr = 0x%08X\n", "CheckBoxPage::OnSetActive", 2665, -2147024882);
  }
  if ( v21 )
    DirectUI::Element::EndDefer(Element, v21);
  return 0;
}

```

## disassembly

```asm
0x14002eed0  push    rbp
0x14002eed2  push    rbx
0x14002eed3  push    rsi
0x14002eed4  push    rdi
0x14002eed5  push    r12
0x14002eed7  push    r13
0x14002eed9  push    r14
0x14002eedb  push    r15
0x14002eedd  mov     rbp, rsp
0x14002eee0  sub     rsp, 78h
0x14002eee4  mov     rax, cs:__security_cookie
0x14002eeeb  xor     rax, rsp
0x14002eeee  mov     [rbp+var_18], rax
0x14002eef2  mov     rsi, rcx
0x14002eef5  mov     [rbp+var_38], 0
0x14002eefd  mov     [rbp+var_48], 0
0x14002ef04  mov     [rbp+hWnd], 0
0x14002ef0c  call    cs:__imp_?GetElement@TaskPage@DirectUI@@IEAAPEAVElement@2@XZ; DirectUI::TaskPage::GetElement(void)
0x14002ef13  nop     dword ptr [rax+rax+00h]
0x14002ef18  mov     [rbp+var_30], rax
0x14002ef1c  mov     [rbp+var_28], 0
0x14002ef23  lea     rdx, [rbp+var_28]
0x14002ef27  mov     rcx, rax
0x14002ef2a  call    cs:__imp_?StartDefer@Element@DirectUI@@QEAAXPEAK@Z; DirectUI::Element::StartDefer(ulong *)
0x14002ef31  nop     dword ptr [rax+rax+00h]
0x14002ef36  nop
0x14002ef37  call    cs:__imp_GetProcessHeap
0x14002ef3e  nop     dword ptr [rax+rax+00h]
0x14002ef43  mov     rcx, rax; hHeap
0x14002ef46  xor     edx, edx; dwFlags
0x14002ef48  mov     r8d, 1800h; dwBytes
0x14002ef4e  call    cs:__imp_HeapAlloc
0x14002ef55  nop     dword ptr [rax+rax+00h]
0x14002ef5a  mov     r13, rax
0x14002ef5d  test    rax, rax
0x14002ef60  jnz     short loc_14002EF8B
0x14002ef62  mov     dword ptr [rsp+78h+var_58], 8007000Eh
0x14002ef6a  mov     r9d, 0A69h
0x14002ef70  lea     r8, aCheckboxpageOn_0; "CheckBoxPage::OnSetActive"
0x14002ef77  lea     rdx, aDwzErrorSDHr0x; "Dwz ERROR: %s:%d - hr = 0x%08X\n"
0x14002ef7e  lea     ecx, [rax+1]; Level
0x14002ef81  call    ?SdpDebugPrint@@YAXKPEBDZZ; SdpDebugPrint(ulong,char const *,...)
0x14002ef86  jmp     loc_14002F22F
0x14002ef8b  call    cs:__imp_GetProcessHeap
0x14002ef92  nop     dword ptr [rax+rax+00h]
0x14002ef97  mov     rcx, rax; hHeap
0x14002ef9a  xor     edx, edx; dwFlags
0x14002ef9c  mov     r8d, 200h; dwBytes
0x14002efa2  call    cs:__imp_HeapAlloc
0x14002efa9  nop     dword ptr [rax+rax+00h]
0x14002efae  mov     r12, rax
0x14002efb1  test    rax, rax
0x14002efb4  jnz     short loc_14002EFD3
0x14002efb6  mov     dword ptr [rsp+78h+var_58], 8007000Eh
0x14002efbe  mov     r9d, 0A6Ah
0x14002efc4  lea     r8, aCheckboxpageOn_0; "CheckBoxPage::OnSetActive"
0x14002efcb  lea     ecx, [rax+1]
0x14002efce  jmp     loc_14002F1DD
0x14002efd3  mov     rcx, rsi; this
0x14002efd6  call    ?OnSetActive@InteractivityPage@@MEAA_JXZ; InteractivityPage::OnSetActive(void)
0x14002efdb  xor     r15d, r15d
0x14002efde  lea     rdi, aCheckboxpageOn_0; "CheckBoxPage::OnSetActive"
0x14002efe5  lea     ebx, [r15+1]
0x14002efe9  mov     r14d, [rsi+0A8h]
0x14002eff0  cmp     r15d, r14d
0x14002eff3  jnb     loc_14002F191
0x14002eff9  lea     eax, [r15+1]
0x14002effd  mov     [rbp+var_44], eax
0x14002f000  mov     r9d, eax
0x14002f003  lea     r8, aCbD; "cb%d"
0x14002f00a  mov     edx, 4; unsigned __int64
0x14002f00f  lea     rcx, [rbp+var_20]; unsigned __int16 *
0x14002f013  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x14002f018  test    eax, eax
0x14002f01a  js      loc_14002F189
0x14002f020  lea     r8, [rbp+var_38]; struct InteractivityChoice **
0x14002f024  mov     edx, r15d; unsigned int
0x14002f027  mov     rcx, rsi; this
0x14002f02a  call    ?GetItem@InteractivityPage@@IEAAJIPEAPEAVInteractivityChoice@@@Z; InteractivityPage::GetItem(uint,InteractivityChoice * *)
0x14002f02f  test    eax, eax
0x14002f031  js      loc_14002F181
0x14002f037  lea     r9, [rbp+var_48]; int *
0x14002f03b  mov     r14, [rbp+var_38]
0x14002f03f  mov     r8, [r14]; unsigned __int16 *
0x14002f042  mov     edx, 100h; unsigned __int64
0x14002f047  mov     rcx, r12; unsigned __int16 *
0x14002f04a  call    ?DwzStrTruncate@@YAJPEAG_KPEBGPEAH@Z; DwzStrTruncate(ushort *,unsigned __int64,ushort const *,int *)
0x14002f04f  test    eax, eax
0x14002f051  js      loc_14002F179
0x14002f057  mov     edx, 0C00h; unsigned __int64
0x14002f05c  mov     rcx, r13; unsigned __int16 *
0x14002f05f  cmp     [rbp+var_48], 0
0x14002f063  jz      short loc_14002F08C
0x14002f065  mov     rax, [r14+8]
0x14002f069  mov     [rsp+78h+var_58], rax
0x14002f06e  mov     r9, [r14]
0x14002f071  lea     r8, aSS_3; "%s\n\n%s"
0x14002f078  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x14002f07d  test    eax, eax
0x14002f07f  jns     short loc_14002F09D
0x14002f081  mov     r9d, 0A8Ah
0x14002f087  jmp     loc_14002F1D4
0x14002f08c  mov     r8, [r14+8]; unsigned __int16 *
0x14002f090  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x14002f095  test    eax, eax
0x14002f097  js      loc_14002F171
0x14002f09d  mov     [rsp+78h+var_50], r13; unsigned __int16 *
0x14002f0a2  mov     r9, [r14]; unsigned __int16 *
0x14002f0a5  mov     r8, r12; unsigned __int16 *
0x14002f0a8  lea     rdx, [rbp+var_20]; unsigned __int16 *
0x14002f0ac  mov     rcx, rsi; this
0x14002f0af  call    ?SetNamedValues@WizardPage@@IEAAJPEBG0000@Z; WizardPage::SetNamedValues(ushort const *,ushort const *,ushort const *,ushort const *,ushort const *)
0x14002f0b4  test    eax, eax
0x14002f0b6  js      loc_14002F169
0x14002f0bc  mov     r8d, ebx; int
0x14002f0bf  lea     rdx, [rbp+var_20]; unsigned __int16 *
0x14002f0c3  mov     rcx, rsi; this
0x14002f0c6  call    ?ShowNamedElement@WizardPage@@IEAAJPEBGH@Z; WizardPage::ShowNamedElement(ushort const *,int)
0x14002f0cb  test    eax, eax
0x14002f0cd  js      loc_14002F161
0x14002f0d3  mov     r8d, ebx; int
0x14002f0d6  lea     rdx, [rbp+var_20]; unsigned __int16 *
0x14002f0da  mov     rcx, rsi; this
0x14002f0dd  call    ?EnableNamedTooltip@WizardPage@@IEAAJPEBGH@Z; WizardPage::EnableNamedTooltip(ushort const *,int)
0x14002f0e2  test    eax, eax
0x14002f0e4  js      short loc_14002F159
0x14002f0e6  lea     r8, [rbp+hWnd]; HWND *
0x14002f0ea  lea     rdx, [rbp+var_20]; unsigned __int16 *
0x14002f0ee  mov     rcx, rsi; this
0x14002f0f1  call    ?GetNamedHandle@WizardPage@@IEAAJPEBGPEAPEAUHWND__@@@Z; WizardPage::GetNamedHandle(ushort const *,HWND__ * *)
0x14002f0f6  test    eax, eax
0x14002f0f8  js      short loc_14002F151
0x14002f0fa  xor     r8d, r8d
0x14002f0fd  cmp     [r14+28h], r8d
0x14002f101  setnz   r8b; wParam
0x14002f105  xor     r9d, r9d; lParam
0x14002f108  mov     edx, 0F1h; Msg
0x14002f10d  mov     rcx, [rbp+hWnd]; hWnd
0x14002f111  call    cs:__imp_PostMessageW
0x14002f118  nop     dword ptr [rax+rax+00h]
0x14002f11d  mov     rdx, [rbp+hWnd]; HWND
0x14002f121  mov     rcx, r14; this
0x14002f124  call    ?MakeButtonImageList@InteractivityChoice@@QEAAJPEAUHWND__@@@Z; InteractivityChoice::MakeButtonImageList(HWND__ *)
0x14002f129  test    eax, eax
0x14002f12b  jns     short loc_14002F148
0x14002f12d  mov     dword ptr [rsp+78h+var_58], eax
0x14002f131  mov     r9d, 0AABh
0x14002f137  mov     r8, rdi
0x14002f13a  lea     rdx, aDwzWarningSDHr; "Dwz WARNING: %s:%d - hr = 0x%08X\n"
0x14002f141  mov     ecx, ebx; Level
0x14002f143  call    ?SdpDebugPrint@@YAXKPEBDZZ; SdpDebugPrint(ulong,char const *,...)
0x14002f148  mov     r15d, [rbp+var_44]
0x14002f14c  jmp     loc_14002EFE9
0x14002f151  mov     r9d, 0AA2h
0x14002f157  jmp     short loc_14002F1D4
0x14002f159  mov     r9d, 0A9Fh
0x14002f15f  jmp     short loc_14002F1D4
0x14002f161  mov     r9d, 0A9Ch
0x14002f167  jmp     short loc_14002F1D4
0x14002f169  mov     r9d, 0A99h
0x14002f16f  jmp     short loc_14002F1D4
0x14002f171  mov     r9d, 0A90h
0x14002f177  jmp     short loc_14002F1D4
0x14002f179  mov     r9d, 0A7Dh
0x14002f17f  jmp     short loc_14002F1D4
0x14002f181  mov     r9d, 0A76h
0x14002f187  jmp     short loc_14002F1D4
0x14002f189  mov     r9d, 0A73h
0x14002f18f  jmp     short loc_14002F1D4
0x14002f191  cmp     r14d, 4
0x14002f195  jnb     short loc_14002F1E9
0x14002f197  inc     r14d
0x14002f19a  mov     r9d, r14d
0x14002f19d  lea     r8, aCbD; "cb%d"
0x14002f1a4  mov     edx, 4; unsigned __int64
0x14002f1a9  lea     rcx, [rbp+var_20]; unsigned __int16 *
0x14002f1ad  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x14002f1b2  test    eax, eax
0x14002f1b4  js      short loc_14002F1CE
0x14002f1b6  lea     rdx, [rbp+var_20]; unsigned __int16 *
0x14002f1ba  mov     rcx, rsi; this
0x14002f1bd  call    ?HideNamedElement@WizardPage@@IEAAJPEBG@Z; WizardPage::HideNamedElement(ushort const *)
0x14002f1c2  test    eax, eax
0x14002f1c4  jns     short loc_14002F191
0x14002f1c6  mov     r9d, 0AB6h
0x14002f1cc  jmp     short loc_14002F1D4
0x14002f1ce  mov     r9d, 0AB3h
0x14002f1d4  mov     dword ptr [rsp+78h+var_58], eax
0x14002f1d8  mov     r8, rdi
0x14002f1db  mov     ecx, ebx; Level
0x14002f1dd  lea     rdx, aDwzErrorSDHr0x; "Dwz ERROR: %s:%d - hr = 0x%08X\n"
0x14002f1e4  call    ?SdpDebugPrint@@YAXKPEBDZZ; SdpDebugPrint(ulong,char const *,...)
0x14002f1e9  call    cs:__imp_GetProcessHeap
0x14002f1f0  nop     dword ptr [rax+rax+00h]
0x14002f1f5  mov     rcx, rax; hHeap
0x14002f1f8  mov     r8, r13; lpMem
0x14002f1fb  xor     edx, edx; dwFlags
0x14002f1fd  call    cs:__imp_HeapFree
0x14002f204  nop     dword ptr [rax+rax+00h]
0x14002f209  test    r12, r12
0x14002f20c  jz      short loc_14002F22F
0x14002f20e  call    cs:__imp_GetProcessHeap
0x14002f215  nop     dword ptr [rax+rax+00h]
0x14002f21a  mov     rcx, rax; hHeap
0x14002f21d  mov     r8, r12; lpMem
0x14002f220  xor     edx, edx; dwFlags
0x14002f222  call    cs:__imp_HeapFree
0x14002f229  nop     dword ptr [rax+rax+00h]
0x14002f22e  nop
0x14002f22f  mov     edx, [rbp+var_28]
0x14002f232  test    edx, edx
0x14002f234  jz      short loc_14002F247
0x14002f236  mov     rcx, [rbp+var_30]
0x14002f23a  call    cs:__imp_?EndDefer@Element@DirectUI@@QEAAXK@Z; DirectUI::Element::EndDefer(ulong)
0x14002f241  nop     dword ptr [rax+rax+00h]
0x14002f246  nop
0x14002f247  xor     eax, eax
0x14002f249  mov     rcx, [rbp+var_18]
0x14002f24d  xor     rcx, rsp; StackCookie
0x14002f250  call    __security_check_cookie
0x14002f255  add     rsp, 78h
0x14002f259  pop     r15
0x14002f25b  pop     r14
0x14002f25d  pop     r13
0x14002f25f  pop     r12
0x14002f261  pop     rdi
0x14002f262  pop     rsi
0x14002f263  pop     rbx
0x14002f264  pop     rbp
0x14002f265  retn
```
