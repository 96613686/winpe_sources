# RadioButtonPage::OnSetActive(void)

- ea: `0x1400309e0`
- end: `0x140030e2e`
- name: `?OnSetActive@RadioButtonPage@@MEAA_JXZ`
- size: `1102`
- prototype: `__int64 __fastcall(RadioButtonPage *__hidden this)`
- caller_count: `0`
- callee_count: `17`
- tags: `service_task`

## callees

- `0x14000706c`
- `0x1400070b0`
- `0x14000e300`
- `0x14000e6bc`
- `0x14000e72c`
- `0x14000e978`
- `0x140010680`
- `0x1400108b0`
- `0x140010a10`
- `0x140020420`
- `0x140020d58`
- `0x14002ad30`
- `0x14002d660`
- `0x14002fc60`
- `0x1400309e0`
- `0x140061c90`
- `0x140063010`

## import_xrefs

- `KERNEL32!HeapAlloc` at `0x140030a4e`
- `KERNEL32!HeapAlloc` at `0x140030aa3`
- `KERNEL32!HeapAlloc` at `0x140030a4e`
- `KERNEL32!HeapAlloc` at `0x140030aa3`
- `KERNEL32!HeapFree` at `0x140030dc1`
- `KERNEL32!HeapFree` at `0x140030de6`
- `KERNEL32!HeapFree` at `0x140030dc1`
- `KERNEL32!HeapFree` at `0x140030de6`
- `KERNEL32!GetProcessHeap` at `0x140030a37`
- `KERNEL32!GetProcessHeap` at `0x140030a8c`
- `KERNEL32!GetProcessHeap` at `0x140030dac`
- `KERNEL32!GetProcessHeap` at `0x140030dd2`
- `KERNEL32!GetProcessHeap` at `0x140030a37`
- `KERNEL32!GetProcessHeap` at `0x140030a8c`
- `KERNEL32!GetProcessHeap` at `0x140030dac`
- `KERNEL32!GetProcessHeap` at `0x140030dd2`
- `USER32!PostMessageW` at `0x140030b88`
- `USER32!PostMessageW` at `0x140030bab`
- `USER32!PostMessageW` at `0x140030b88`
- `USER32!PostMessageW` at `0x140030bab`
- `DUI70!?EndDefer@Element@DirectUI@@QEAAXK@Z` at `0x140030dfe`
- `DUI70!?EndDefer@Element@DirectUI@@QEAAXK@Z` at `0x140030dfe`
- `DUI70!?StartDefer@Element@DirectUI@@QEAAXPEAK@Z` at `0x140030a2a`
- `DUI70!?StartDefer@Element@DirectUI@@QEAAXPEAK@Z` at `0x140030a2a`
- `DUI70!?PropSheet_SendMessage@TaskPage@DirectUI@@IEAA_JI_K_J@Z` at `0x140030d51`
- `DUI70!?PropSheet_SendMessage@TaskPage@DirectUI@@IEAA_JI_K_J@Z` at `0x140030d51`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall RadioButtonPage::OnSetActive(RadioButtonPage *this)
{
  HANDLE ProcessHeap; // rax
  HANDLE v3; // rax
  unsigned __int16 *v4; // r13
  int v5; // r12d
  unsigned int v6; // r15d
  unsigned int v7; // r14d
  int NamedHandle; // eax
  const unsigned __int16 **v9; // r14
  HWND v10; // r15
  int v11; // r9d
  int ButtonImageList; // eax
  HANDLE v13; // rax
  HANDLE v14; // rax
  const unsigned __int16 *v16; // [rsp+20h] [rbp-49h]
  int v17; // [rsp+30h] [rbp-39h] BYREF
  LPVOID lpMem; // [rsp+38h] [rbp-31h]
  unsigned int v19; // [rsp+40h] [rbp-29h]
  HWND hWnd; // [rsp+48h] [rbp-21h] BYREF
  struct InteractivityChoice *v21; // [rsp+50h] [rbp-19h] BYREF
  struct DirectUI::Element *v22; // [rsp+58h] [rbp-11h] BYREF
  DirectUI::Element *v23; // [rsp+60h] [rbp-9h]
  unsigned int v24; // [rsp+68h] [rbp-1h] BYREF
  unsigned __int16 v25; // [rsp+70h] [rbp+7h] BYREF

  v21 = 0;
  v17 = 0;
  hWnd = 0;
  v22 = 0;
  v23 = (DirectUI::Element *)*((_QWORD *)this + 8);
  v24 = 0;
  DirectUI::Element::StartDefer(v23, &v24);
  ProcessHeap = GetProcessHeap();
  lpMem = HeapAlloc(ProcessHeap, 0, 0x1800u);
  if ( !lpMem )
  {
    SdpDebugPrint(1u, "Dwz ERROR: %s:%d - hr = 0x%08X\n", "RadioButtonPage::OnSetActive", 1886, -2147024882);
    goto LABEL_43;
  }
  v3 = GetProcessHeap();
  v4 = (unsigned __int16 *)HeapAlloc(v3, 0, 0x200u);
  if ( !v4 )
  {
    SdpDebugPrint(1u, "Dwz ERROR: %s:%d - hr = 0x%08X\n", "RadioButtonPage::OnSetActive", 1887, -2147024882);
    goto LABEL_41;
  }
  v5 = 0;
  WizardPage::StartRetireBannerTipTest(this, 3);
  InteractivityPage::OnSetActive(this);
  *((_DWORD *)this + 46) = 1;
  v6 = 0;
  v7 = *((_DWORD *)this + 42);
  if ( !v7 )
    goto LABEL_25;
  do
  {
    v19 = v6 + 1;
    NamedHandle = StringCchPrintfW(&v25, 4u, L"rb%d", v6 + 1);
    if ( NamedHandle < 0 )
    {
      v11 = 1903;
      goto LABEL_40;
    }
    NamedHandle = WizardPage::GetNamedHandle(this, &v25, &hWnd);
    if ( NamedHandle < 0 )
    {
      v11 = 1906;
      goto LABEL_40;
    }
    NamedHandle = InteractivityPage::GetItem(this, v6, &v21);
    if ( NamedHandle < 0 )
    {
      v11 = 1909;
      goto LABEL_40;
    }
    v9 = (const unsigned __int16 **)v21;
    if ( v5 || !*((_DWORD *)v21 + 10) )
    {
      v10 = hWnd;
      PostMessageW(hWnd, 0xF1u, 0, 0);
    }
    else
    {
      v10 = hWnd;
      PostMessageW(hWnd, 0xF1u, 1u, 0);
      v5 = 1;
    }
    NamedHandle = DwzStrTruncate(v4, 0x100u, *v9, &v17);
    if ( NamedHandle < 0 )
    {
      v11 = 1927;
      goto LABEL_40;
    }
    if ( v17 )
    {
      v16 = v9[1];
      NamedHandle = StringCchPrintfW((unsigned __int16 *)lpMem, 0xC00u, L"%s\n\n%s", *v9);
      if ( NamedHandle < 0 )
      {
        v11 = 1936;
LABEL_40:
        SdpDebugPrint(1u, "Dwz ERROR: %s:%d - hr = 0x%08X\n", "RadioButtonPage::OnSetActive", v11, NamedHandle);
        goto LABEL_41;
      }
    }
    else
    {
      NamedHandle = StringCchCopyW((unsigned __int16 *)lpMem, 0xC00u, v9[1]);
      if ( NamedHandle < 0 )
      {
        v11 = 1942;
        goto LABEL_40;
      }
    }
    NamedHandle = WizardPage::SetNamedValues(this, &v25, v4, *v9, v16, (const unsigned __int16 *)lpMem);
    if ( NamedHandle < 0 )
    {
      v11 = 1951;
      goto LABEL_40;
    }
    NamedHandle = WizardPage::ShowNamedElement(this, &v25, 1);
    if ( NamedHandle < 0 )
    {
      v11 = 1954;
      goto LABEL_40;
    }
    NamedHandle = WizardPage::EnableNamedTooltip(this, &v25, 1);
    if ( NamedHandle < 0 )
    {
      v11 = 1957;
      goto LABEL_40;
    }
    ButtonImageList = InteractivityChoice::MakeButtonImageList((InteractivityChoice *)v9, v10);
    if ( ButtonImageList < 0 )
      SdpDebugPrint(1u, "Dwz WARNING: %s:%d - hr = 0x%08X\n", "RadioButtonPage::OnSetActive", 1960, ButtonImageList);
    v6 = v19;
    v7 = *((_DWORD *)this + 42);
  }
  while ( v19 < v7 );
  while ( v7 < 4 )
  {
LABEL_25:
    NamedHandle = StringCchPrintfW(&v25, 4u, L"rb%d", ++v7);
    if ( NamedHandle < 0 )
    {
      v11 = 1966;
      goto LABEL_40;
    }
    NamedHandle = WizardPage::HideNamedElement(this, &v25);
    if ( NamedHandle < 0 )
    {
      v11 = 1969;
      goto LABEL_40;
    }
  }
  DirectUI::TaskPage::PropSheet_SendMessage(this, 0x48Bu, -(__int64)(v5 != 0) & 2, 2);
  NamedHandle = WizardPage::GetNamedElement(this, L"rb1", &v22);
  if ( NamedHandle < 0 )
  {
    v11 = 1981;
    goto LABEL_40;
  }
  (*(void (__fastcall **)(struct DirectUI::Element *))(*(_QWORD *)v22 + 168LL))(v22);
LABEL_41:
  v13 = GetProcessHeap();
  HeapFree(v13, 0, lpMem);
  if ( v4 )
  {
    v14 = GetProcessHeap();
    HeapFree(v14, 0, v4);
  }
LABEL_43:
  if ( v24 )
    DirectUI::Element::EndDefer(v23, v24);
  return 0;
}

```

## disassembly

```asm
0x1400309e0  push    rbp
0x1400309e2  push    rbx
0x1400309e3  push    rsi
0x1400309e4  push    rdi
0x1400309e5  push    r12
0x1400309e7  push    r13
0x1400309e9  push    r14
0x1400309eb  push    r15
0x1400309ed  lea     rbp, [rsp-1Fh]
0x1400309f2  sub     rsp, 88h
0x1400309f9  mov     rax, cs:__security_cookie
0x140030a00  xor     rax, rsp
0x140030a03  mov     [rbp+57h+var_48], rax
0x140030a07  mov     rsi, rcx
0x140030a0a  xor     edi, edi
0x140030a0c  mov     [rbp+57h+var_70], rdi
0x140030a10  mov     [rbp+57h+var_90], edi
0x140030a13  mov     [rbp+57h+hWnd], rdi
0x140030a17  mov     [rbp+57h+var_68], rdi
0x140030a1b  mov     rcx, [rcx+40h]
0x140030a1f  mov     [rbp+57h+var_60], rcx
0x140030a23  mov     [rbp+57h+var_58], edi
0x140030a26  lea     rdx, [rbp+57h+var_58]
0x140030a2a  call    cs:__imp_?StartDefer@Element@DirectUI@@QEAAXPEAK@Z; DirectUI::Element::StartDefer(ulong *)
0x140030a31  nop     dword ptr [rax+rax+00h]
0x140030a36  nop
0x140030a37  call    cs:__imp_GetProcessHeap
0x140030a3e  nop     dword ptr [rax+rax+00h]
0x140030a43  mov     rcx, rax; hHeap
0x140030a46  xor     edx, edx; dwFlags
0x140030a48  mov     r8d, 1800h; dwBytes
0x140030a4e  call    cs:__imp_HeapAlloc
0x140030a55  nop     dword ptr [rax+rax+00h]
0x140030a5a  mov     [rbp+57h+lpMem], rax
0x140030a5e  test    rax, rax
0x140030a61  jnz     short loc_140030A8C
0x140030a63  mov     dword ptr [rsp+0C0h+var_A0], 8007000Eh
0x140030a6b  mov     r9d, 75Eh
0x140030a71  lea     r8, aRadiobuttonpag; "RadioButtonPage::OnSetActive"
0x140030a78  lea     rdx, aDwzErrorSDHr0x; "Dwz ERROR: %s:%d - hr = 0x%08X\n"
0x140030a7f  lea     ecx, [rdi+1]; Level
0x140030a82  call    ?SdpDebugPrint@@YAXKPEBDZZ; SdpDebugPrint(ulong,char const *,...)
0x140030a87  jmp     loc_140030DF3
0x140030a8c  call    cs:__imp_GetProcessHeap
0x140030a93  nop     dword ptr [rax+rax+00h]
0x140030a98  mov     rcx, rax; hHeap
0x140030a9b  xor     edx, edx; dwFlags
0x140030a9d  mov     r8d, 200h; dwBytes
0x140030aa3  call    cs:__imp_HeapAlloc
0x140030aaa  nop     dword ptr [rax+rax+00h]
0x140030aaf  mov     r13, rax
0x140030ab2  test    rax, rax
0x140030ab5  jnz     short loc_140030AD4
0x140030ab7  mov     dword ptr [rsp+0C0h+var_A0], 8007000Eh
0x140030abf  mov     r9d, 75Fh
0x140030ac5  lea     r8, aRadiobuttonpag; "RadioButtonPage::OnSetActive"
0x140030acc  lea     ecx, [rax+1]
0x140030acf  jmp     loc_140030DA0
0x140030ad4  mov     r12d, edi
0x140030ad7  mov     edx, 3
0x140030adc  mov     rcx, rsi
0x140030adf  call    ?StartRetireBannerTipTest@WizardPage@@IEAAXW4PageNames@@@Z; WizardPage::StartRetireBannerTipTest(PageNames)
0x140030ae4  mov     rcx, rsi; this
0x140030ae7  call    ?OnSetActive@InteractivityPage@@MEAA_JXZ; InteractivityPage::OnSetActive(void)
0x140030aec  mov     ebx, 1
0x140030af1  mov     [rsi+0B8h], ebx
0x140030af7  mov     r15d, edi
0x140030afa  mov     r14d, [rsi+0A8h]
0x140030b01  lea     rdi, aRadiobuttonpag; "RadioButtonPage::OnSetActive"
0x140030b08  test    r14d, r14d
0x140030b0b  jz      loc_140030CB3
0x140030b11  lea     eax, [r15+1]
0x140030b15  mov     [rbp+57h+var_80], eax
0x140030b18  mov     r9d, eax
0x140030b1b  lea     r8, aRbD; "rb%d"
0x140030b22  mov     edx, 4; unsigned __int64
0x140030b27  lea     rcx, [rbp+57h+var_50]; unsigned __int16 *
0x140030b2b  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x140030b30  test    eax, eax
0x140030b32  js      loc_140030D32
0x140030b38  lea     r8, [rbp+57h+hWnd]; HWND *
0x140030b3c  lea     rdx, [rbp+57h+var_50]; unsigned __int16 *
0x140030b40  mov     rcx, rsi; this
0x140030b43  call    ?GetNamedHandle@WizardPage@@IEAAJPEBGPEAPEAUHWND__@@@Z; WizardPage::GetNamedHandle(ushort const *,HWND__ * *)
0x140030b48  test    eax, eax
0x140030b4a  js      loc_140030D2A
0x140030b50  lea     r8, [rbp+57h+var_70]; struct InteractivityChoice **
0x140030b54  mov     edx, r15d; unsigned int
0x140030b57  mov     rcx, rsi; this
0x140030b5a  call    ?GetItem@InteractivityPage@@IEAAJIPEAPEAVInteractivityChoice@@@Z; InteractivityPage::GetItem(uint,InteractivityChoice * *)
0x140030b5f  test    eax, eax
0x140030b61  js      loc_140030D22
0x140030b67  mov     r14, [rbp+57h+var_70]
0x140030b6b  test    r12d, r12d
0x140030b6e  jnz     short loc_140030B99
0x140030b70  cmp     [r14+28h], r12d
0x140030b74  jz      short loc_140030B99
0x140030b76  xor     r9d, r9d; lParam
0x140030b79  mov     r8, rbx; wParam
0x140030b7c  mov     edx, 0F1h; Msg
0x140030b81  mov     r15, [rbp+57h+hWnd]
0x140030b85  mov     rcx, r15; hWnd
0x140030b88  call    cs:__imp_PostMessageW
0x140030b8f  nop     dword ptr [rax+rax+00h]
0x140030b94  mov     r12d, ebx
0x140030b97  jmp     short loc_140030BB7
0x140030b99  xor     r9d, r9d; lParam
0x140030b9c  xor     r8d, r8d; wParam
0x140030b9f  mov     edx, 0F1h; Msg
0x140030ba4  mov     r15, [rbp+57h+hWnd]
0x140030ba8  mov     rcx, r15; hWnd
0x140030bab  call    cs:__imp_PostMessageW
0x140030bb2  nop     dword ptr [rax+rax+00h]
0x140030bb7  lea     r9, [rbp+57h+var_90]; int *
0x140030bbb  mov     r8, [r14]; unsigned __int16 *
0x140030bbe  mov     edx, 100h; unsigned __int64
0x140030bc3  mov     rcx, r13; unsigned __int16 *
0x140030bc6  call    ?DwzStrTruncate@@YAJPEAG_KPEBGPEAH@Z; DwzStrTruncate(ushort *,unsigned __int64,ushort const *,int *)
0x140030bcb  test    eax, eax
0x140030bcd  js      loc_140030D1A
0x140030bd3  mov     edx, 0C00h; unsigned __int64
0x140030bd8  mov     rcx, [rbp+57h+lpMem]; unsigned __int16 *
0x140030bdc  cmp     [rbp+57h+var_90], 0
0x140030be0  jz      short loc_140030C09
0x140030be2  mov     rax, [r14+8]
0x140030be6  mov     [rsp+0C0h+var_A0], rax
0x140030beb  mov     r9, [r14]
0x140030bee  lea     r8, aSS_3; "%s\n\n%s"
0x140030bf5  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x140030bfa  test    eax, eax
0x140030bfc  jns     short loc_140030C1A
0x140030bfe  mov     r9d, 790h
0x140030c04  jmp     loc_140030D97
0x140030c09  mov     r8, [r14+8]; unsigned __int16 *
0x140030c0d  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x140030c12  test    eax, eax
0x140030c14  js      loc_140030D12
0x140030c1a  mov     rax, [rbp+57h+lpMem]
0x140030c1e  mov     [rsp+0C0h+var_98], rax; unsigned __int16 *
0x140030c23  mov     r9, [r14]; unsigned __int16 *
0x140030c26  mov     r8, r13; unsigned __int16 *
0x140030c29  lea     rdx, [rbp+57h+var_50]; unsigned __int16 *
0x140030c2d  mov     rcx, rsi; this
0x140030c30  call    ?SetNamedValues@WizardPage@@IEAAJPEBG0000@Z; WizardPage::SetNamedValues(ushort const *,ushort const *,ushort const *,ushort const *,ushort const *)
0x140030c35  test    eax, eax
0x140030c37  js      loc_140030D07
0x140030c3d  mov     r8d, ebx; int
0x140030c40  lea     rdx, [rbp+57h+var_50]; unsigned __int16 *
0x140030c44  mov     rcx, rsi; this
0x140030c47  call    ?ShowNamedElement@WizardPage@@IEAAJPEBGH@Z; WizardPage::ShowNamedElement(ushort const *,int)
0x140030c4c  test    eax, eax
0x140030c4e  js      loc_140030CFC
0x140030c54  mov     r8d, ebx; int
0x140030c57  lea     rdx, [rbp+57h+var_50]; unsigned __int16 *
0x140030c5b  mov     rcx, rsi; this
0x140030c5e  call    ?EnableNamedTooltip@WizardPage@@IEAAJPEBGH@Z; WizardPage::EnableNamedTooltip(ushort const *,int)
0x140030c63  test    eax, eax
0x140030c65  js      loc_140030CF1
0x140030c6b  mov     rdx, r15; HWND
0x140030c6e  mov     rcx, r14; this
0x140030c71  call    ?MakeButtonImageList@InteractivityChoice@@QEAAJPEAUHWND__@@@Z; InteractivityChoice::MakeButtonImageList(HWND__ *)
0x140030c76  test    eax, eax
0x140030c78  jns     short loc_140030C95
0x140030c7a  mov     dword ptr [rsp+0C0h+var_A0], eax
0x140030c7e  mov     r9d, 7A8h
0x140030c84  mov     r8, rdi
0x140030c87  lea     rdx, aDwzWarningSDHr; "Dwz WARNING: %s:%d - hr = 0x%08X\n"
0x140030c8e  mov     ecx, ebx; Level
0x140030c90  call    ?SdpDebugPrint@@YAXKPEBDZZ; SdpDebugPrint(ulong,char const *,...)
0x140030c95  mov     r15d, [rbp+57h+var_80]
0x140030c99  mov     r14d, [rsi+0A8h]
0x140030ca0  cmp     r15d, r14d
0x140030ca3  jb      loc_140030B11
0x140030ca9  cmp     r14d, 4
0x140030cad  jnb     loc_140030D3A
0x140030cb3  inc     r14d
0x140030cb6  mov     r9d, r14d
0x140030cb9  lea     r8, aRbD; "rb%d"
0x140030cc0  mov     edx, 4; unsigned __int64
0x140030cc5  lea     rcx, [rbp+57h+var_50]; unsigned __int16 *
0x140030cc9  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x140030cce  test    eax, eax
0x140030cd0  js      loc_140030D91
0x140030cd6  lea     rdx, [rbp+57h+var_50]; unsigned __int16 *
0x140030cda  mov     rcx, rsi; this
0x140030cdd  call    ?HideNamedElement@WizardPage@@IEAAJPEBG@Z; WizardPage::HideNamedElement(ushort const *)
0x140030ce2  test    eax, eax
0x140030ce4  jns     short loc_140030CA9
0x140030ce6  mov     r9d, 7B1h
0x140030cec  jmp     loc_140030D97
0x140030cf1  mov     r9d, 7A5h
0x140030cf7  jmp     loc_140030D97
0x140030cfc  mov     r9d, 7A2h
0x140030d02  jmp     loc_140030D97
0x140030d07  mov     r9d, 79Fh
0x140030d0d  jmp     loc_140030D97
0x140030d12  mov     r9d, 796h
0x140030d18  jmp     short loc_140030D97
0x140030d1a  mov     r9d, 787h
0x140030d20  jmp     short loc_140030D97
0x140030d22  mov     r9d, 775h
0x140030d28  jmp     short loc_140030D97
0x140030d2a  mov     r9d, 772h
0x140030d30  jmp     short loc_140030D97
0x140030d32  mov     r9d, 76Fh
0x140030d38  jmp     short loc_140030D97
0x140030d3a  neg     r12d
0x140030d3d  sbb     r8, r8
0x140030d40  mov     r9d, 2
0x140030d46  and     r8, r9
0x140030d49  mov     edx, 48Bh
0x140030d4e  mov     rcx, rsi
0x140030d51  call    cs:__imp_?PropSheet_SendMessage@TaskPage@DirectUI@@IEAA_JI_K_J@Z; DirectUI::TaskPage::PropSheet_SendMessage(uint,unsigned __int64,__int64)
0x140030d58  nop     dword ptr [rax+rax+00h]
0x140030d5d  lea     r8, [rbp+57h+var_68]; struct DirectUI::Element **
0x140030d61  lea     rdx, aRb1; "rb1"
0x140030d68  mov     rcx, rsi; this
0x140030d6b  call    ?GetNamedElement@WizardPage@@QEAAJPEBGPEAPEAVElement@DirectUI@@@Z; WizardPage::GetNamedElement(ushort const *,DirectUI::Element * *)
0x140030d70  test    eax, eax
0x140030d72  jns     short loc_140030D7C
0x140030d74  mov     r9d, 7BDh
0x140030d7a  jmp     short loc_140030D97
0x140030d7c  mov     rcx, [rbp+57h+var_68]
0x140030d80  mov     rax, [rcx]
0x140030d83  mov     rax, [rax+0A8h]
0x140030d8a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140030d8f  jmp     short loc_140030DAC
0x140030d91  mov     r9d, 7AEh
0x140030d97  mov     ecx, ebx; Level
0x140030d99  mov     r8, rdi
0x140030d9c  mov     dword ptr [rsp+0C0h+var_A0], eax
0x140030da0  lea     rdx, aDwzErrorSDHr0x; "Dwz ERROR: %s:%d - hr = 0x%08X\n"
0x140030da7  call    ?SdpDebugPrint@@YAXKPEBDZZ; SdpDebugPrint(ulong,char const *,...)
0x140030dac  call    cs:__imp_GetProcessHeap
0x140030db3  nop     dword ptr [rax+rax+00h]
0x140030db8  mov     rcx, rax; hHeap
0x140030dbb  mov     r8, [rbp+57h+lpMem]; lpMem
0x140030dbf  xor     edx, edx; dwFlags
0x140030dc1  call    cs:__imp_HeapFree
0x140030dc8  nop     dword ptr [rax+rax+00h]
0x140030dcd  test    r13, r13
0x140030dd0  jz      short loc_140030DF3
0x140030dd2  call    cs:__imp_GetProcessHeap
0x140030dd9  nop     dword ptr [rax+rax+00h]
0x140030dde  mov     rcx, rax; hHeap
0x140030de1  mov     r8, r13; lpMem
0x140030de4  xor     edx, edx; dwFlags
0x140030de6  call    cs:__imp_HeapFree
0x140030ded  nop     dword ptr [rax+rax+00h]
0x140030df2  nop
0x140030df3  mov     edx, [rbp+57h+var_58]
0x140030df6  test    edx, edx
0x140030df8  jz      short loc_140030E0B
0x140030dfa  mov     rcx, [rbp+57h+var_60]
0x140030dfe  call    cs:__imp_?EndDefer@Element@DirectUI@@QEAAXK@Z; DirectUI::Element::EndDefer(ulong)
0x140030e05  nop     dword ptr [rax+rax+00h]
0x140030e0a  nop
0x140030e0b  xor     eax, eax
0x140030e0d  mov     rcx, [rbp+57h+var_48]
0x140030e11  xor     rcx, rsp; StackCookie
0x140030e14  call    __security_check_cookie
0x140030e19  add     rsp, 88h
0x140030e20  pop     r15
0x140030e22  pop     r14
0x140030e24  pop     r13
0x140030e26  pop     r12
0x140030e28  pop     rdi
0x140030e29  pop     rsi
0x140030e2a  pop     rbx
0x140030e2b  pop     rbp
0x140030e2c  retn
```
