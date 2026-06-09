# FinalLinksPage::OnSetActive(void)

- ea: `0x14001af10`
- end: `0x14001b2da`
- name: `?OnSetActive@FinalLinksPage@@MEAA_JXZ`
- size: `970`
- prototype: `__int64 __fastcall(FinalLinksPage *__hidden this)`
- caller_count: `4`
- callee_count: `12`
- tags: `registry_config`

## callers

- `0x14001ae60`
- `0x14001b2e0`
- `0x14001b360`
- `0x14001cf60`

## callees

- `0x14000e0f0`
- `0x14000e978`
- `0x14000f480`
- `0x140010680`
- `0x140010a10`
- `0x140019710`
- `0x14001a290`
- `0x14001af10`
- `0x140020420`
- `0x14004175c`
- `0x140041c54`
- `0x140063010`

## import_xrefs

- `KERNEL32!HeapAlloc` at `0x14001afca`
- `KERNEL32!HeapAlloc` at `0x14001b0a2`
- `KERNEL32!HeapAlloc` at `0x14001afca`
- `KERNEL32!HeapAlloc` at `0x14001b0a2`
- `KERNEL32!HeapFree` at `0x14001b29f`
- `KERNEL32!HeapFree` at `0x14001b29f`
- `KERNEL32!GetProcessHeap` at `0x14001afb6`
- `KERNEL32!GetProcessHeap` at `0x14001b08e`
- `KERNEL32!GetProcessHeap` at `0x14001b28b`
- `KERNEL32!GetProcessHeap` at `0x14001afb6`
- `KERNEL32!GetProcessHeap` at `0x14001b08e`
- `KERNEL32!GetProcessHeap` at `0x14001b28b`
- `USER32!SendMessageW` at `0x14001b200`
- `USER32!SendMessageW` at `0x14001b200`
- `DUI70!?Destroy@DUIXmlParser@DirectUI@@QEAAXXZ` at `0x14001b272`
- `DUI70!?Destroy@DUIXmlParser@DirectUI@@QEAAXXZ` at `0x14001b272`
- `DUI70!StrToID` at `0x14001b1ba`
- `DUI70!StrToID` at `0x14001b1ba`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x14001b1cc`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x14001b1cc`
- `DUI70!?EndDefer@Element@DirectUI@@QEAAXK@Z` at `0x14001b2b7`
- `DUI70!?EndDefer@Element@DirectUI@@QEAAXK@Z` at `0x14001b2b7`
- `DUI70!?StartDefer@Element@DirectUI@@QEAAXPEAK@Z` at `0x14001af40`
- `DUI70!?StartDefer@Element@DirectUI@@QEAAXPEAK@Z` at `0x14001af40`

## string_xrefs

- `0x14001b253`: `FinalLinksPage::OnSetActive`
- `0x14001b174`: `nofeedbackQuestionLinks`
- `0x14001b18e`: `nofeedbackQuestionLinks`
- `0x14001b1b3`: `linkElevate`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall FinalLinksPage::OnSetActive(FinalLinksPage *this)
{
  WCHAR *v2; // rsi
  int LocalString; // eax
  int v4; // r9d
  HANDLE ProcessHeap; // rax
  UINT v6; // eax
  HANDLE v7; // rax
  DirectUI::Element *v8; // rbx
  unsigned __int16 v9; // ax
  struct DirectUI::Element *Descendent; // rax
  HWND v11; // rax
  Configuration *v12; // rax
  HANDLE v13; // rax
  const unsigned __int16 *v15; // [rsp+20h] [rbp-20h]
  DirectUI::Element *v16; // [rsp+30h] [rbp-10h]
  unsigned int v17; // [rsp+38h] [rbp-8h] BYREF
  WINBOOL IsMember; // [rsp+60h] [rbp+20h] BYREF
  struct DirectUI::DUIXmlParser *v19; // [rsp+68h] [rbp+28h] BYREF

  v2 = 0;
  IsMember = 0;
  v19 = 0;
  v16 = (DirectUI::Element *)*((_QWORD *)this + 8);
  v17 = 0;
  DirectUI::Element::StartDefer(v16, &v17);
  WizardPage::StartRetireBannerTipTest(this, 1);
  WizardPage::OnSetActive(this);
  LocalString = WizardPage::CloseButton(this);
  if ( LocalString >= 0 )
  {
    if ( (*(unsigned int (__fastcall **)(FinalLinksPage *))(*(_QWORD *)this + 264LL))(this) )
    {
      ProcessHeap = GetProcessHeap();
      v2 = (WCHAR *)HeapAlloc(ProcessHeap, 0, 0x800u);
      if ( !v2 )
      {
        SdpDebugPrint(1u, "Dwz ERROR: %s:%d - hr = 0x%08X\n", "FinalLinksPage::OnSetActive", 72, -2147024882);
        goto LABEL_37;
      }
      v6 = (*(__int64 (__fastcall **)(FinalLinksPage *))(*(_QWORD *)this + 264LL))(this);
      LocalString = DwzLoadLocalString(v6, v2, 0x400u);
      if ( LocalString < 0 )
      {
        v4 = 75;
        goto LABEL_36;
      }
      LocalString = WizardPage::SetNamedValues(this, L"finalSubtext", v2, 0, v15, 0);
      if ( LocalString < 0 )
      {
        v4 = 78;
        goto LABEL_36;
      }
    }
    else
    {
      LocalString = WizardPage::HideNamedElement(this, L"finalSubtext");
      if ( LocalString < 0 )
      {
        v4 = 70;
        goto LABEL_36;
      }
    }
    LocalString = (*(__int64 (__fastcall **)(FinalLinksPage *, struct DirectUI::DUIXmlParser **))(*(_QWORD *)this + 56LL))(
                    this,
                    &v19);
    if ( LocalString >= 0 )
    {
      if ( (*(unsigned int (__fastcall **)(FinalLinksPage *))(*(_QWORD *)this + 280LL))(this) )
      {
        if ( !v2 )
        {
          v7 = GetProcessHeap();
          v2 = (WCHAR *)HeapAlloc(v7, 0, 0x800u);
          if ( !v2 )
          {
            SdpDebugPrint(1u, "Dwz ERROR: %s:%d - hr = 0x%08X\n", "FinalLinksPage::OnSetActive", 89, -2147024882);
            goto LABEL_37;
          }
        }
        LocalString = DwzLoadLocalString(0x284Bu, v2, 0x400u);
        if ( LocalString < 0 )
        {
          v4 = 93;
          goto LABEL_36;
        }
        LocalString = WizardPage::SetNamedValues(this, L"feedbackQuestion", v2, 0, v15, 0);
        if ( LocalString < 0 )
        {
          v4 = 96;
          goto LABEL_36;
        }
      }
      else
      {
        LocalString = WizardPage::HideNamedElement(this, L"feedbackQuestion");
        if ( LocalString < 0 )
        {
          v4 = 101;
          goto LABEL_36;
        }
        LocalString = WizardPage::HideNamedElement(this, L"btnYes");
        if ( LocalString < 0 )
        {
          v4 = 105;
          goto LABEL_36;
        }
        LocalString = WizardPage::HideNamedElement(this, L"btnNo");
        if ( LocalString < 0 )
        {
          v4 = 107;
          goto LABEL_36;
        }
        if ( (int)FinalLinksPage::CreateLinks(this, v19, 1, L"nofeedbackQuestionLinks") < 0 )
        {
          LocalString = FinalLinksPage::CreateLinks(this, v19, 1, L"nofeedbackQuestionLinks");
          v4 = 110;
          goto LABEL_36;
        }
      }
      v8 = (DirectUI::Element *)*((_QWORD *)this + 8);
      v9 = StrToID(L"linkElevate");
      Descendent = DirectUI::Element::FindDescendent(v8, v9);
      if ( Descendent )
      {
        v11 = (HWND)(*(__int64 (__fastcall **)(struct DirectUI::Element *))(*(_QWORD *)Descendent + 360LL))(Descendent);
        SendMessageW(v11, 0x160Cu, 0, 1);
      }
      LocalString = IsAdminToken(&IsMember);
      if ( LocalString >= 0 )
      {
        v12 = Config;
        *((_DWORD *)Config + 49) = 2;
        *((_DWORD *)v12 + 11) = 0;
        LocalString = FinalLinksPage::AddRootCauses(this, v19);
        if ( LocalString >= 0 )
          goto LABEL_37;
        v4 = 136;
      }
      else
      {
        v4 = 120;
      }
    }
    else
    {
      v4 = 82;
    }
  }
  else
  {
    v4 = 63;
  }
LABEL_36:
  SdpDebugPrint(1u, "Dwz ERROR: %s:%d - hr = 0x%08X\n", "FinalLinksPage::OnSetActive", v4, LocalString);
LABEL_37:
  if ( v19 )
  {
    DirectUI::DUIXmlParser::Destroy(v19);
    v19 = 0;
  }
  if ( v2 )
  {
    v13 = GetProcessHeap();
    HeapFree(v13, 0, v2);
  }
  if ( v17 )
    DirectUI::Element::EndDefer(v16, v17);
  return 0;
}

```

## disassembly

```asm
0x14001af10  mov     [rsp-18h+arg_10], rbx
0x14001af15  mov     [rsp-18h+arg_18], rsi
0x14001af1a  push    rbp
0x14001af1b  push    rdi
0x14001af1c  push    r15
0x14001af1e  mov     rbp, rsp
0x14001af21  sub     rsp, 40h
0x14001af25  mov     rdi, rcx
0x14001af28  xor     esi, esi
0x14001af2a  mov     [rbp+IsMember], esi
0x14001af2d  mov     [rbp+arg_8], rsi
0x14001af31  mov     rcx, [rcx+40h]
0x14001af35  mov     [rbp+var_10], rcx
0x14001af39  mov     [rbp+var_8], esi
0x14001af3c  lea     rdx, [rbp+var_8]
0x14001af40  call    cs:__imp_?StartDefer@Element@DirectUI@@QEAAXPEAK@Z; DirectUI::Element::StartDefer(ulong *)
0x14001af47  nop     dword ptr [rax+rax+00h]
0x14001af4c  nop
0x14001af4d  lea     r15d, [rsi+1]
0x14001af51  mov     edx, r15d
0x14001af54  mov     rcx, rdi
0x14001af57  call    ?StartRetireBannerTipTest@WizardPage@@IEAAXW4PageNames@@@Z; WizardPage::StartRetireBannerTipTest(PageNames)
0x14001af5c  mov     rcx, rdi; this
0x14001af5f  call    ?OnSetActive@WizardPage@@MEAA_JXZ; WizardPage::OnSetActive(void)
0x14001af64  mov     rcx, rdi; this
0x14001af67  call    ?CloseButton@WizardPage@@IEAAJXZ; WizardPage::CloseButton(void)
0x14001af6c  test    eax, eax
0x14001af6e  jns     short loc_14001AF79
0x14001af70  lea     r9d, [rsi+3Fh]
0x14001af74  jmp     loc_14001B24F
0x14001af79  mov     rax, [rdi]
0x14001af7c  mov     rcx, rdi
0x14001af7f  mov     rax, [rax+108h]
0x14001af86  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001af8b  mov     ebx, 800h
0x14001af90  test    eax, eax
0x14001af92  jnz     short loc_14001AFB6
0x14001af94  lea     rdx, aFinalsubtext; "finalSubtext"
0x14001af9b  mov     rcx, rdi; this
0x14001af9e  call    ?HideNamedElement@WizardPage@@IEAAJPEBG@Z; WizardPage::HideNamedElement(ushort const *)
0x14001afa3  test    eax, eax
0x14001afa5  jns     loc_14001B04D
0x14001afab  mov     r9d, 46h ; 'F'
0x14001afb1  jmp     loc_14001B24F
0x14001afb6  call    cs:__imp_GetProcessHeap
0x14001afbd  nop     dword ptr [rax+rax+00h]
0x14001afc2  mov     rcx, rax; hHeap
0x14001afc5  mov     r8, rbx; dwBytes
0x14001afc8  xor     edx, edx; dwFlags
0x14001afca  call    cs:__imp_HeapAlloc
0x14001afd1  nop     dword ptr [rax+rax+00h]
0x14001afd6  mov     rsi, rax
0x14001afd9  test    rax, rax
0x14001afdc  jnz     short loc_14001AFEF
0x14001afde  mov     dword ptr [rsp+40h+var_20], 8007000Eh
0x14001afe6  lea     r9d, [rax+48h]
0x14001afea  jmp     loc_14001B253
0x14001afef  mov     rax, [rdi]
0x14001aff2  mov     rcx, rdi
0x14001aff5  mov     rax, [rax+108h]
0x14001affc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001b001  mov     ecx, eax; uID
0x14001b003  mov     r8d, 400h; cchBufferMax
0x14001b009  mov     rdx, rsi; lpBuffer
0x14001b00c  call    ?DwzLoadLocalString@@YAJIPEAG_K@Z; DwzLoadLocalString(uint,ushort *,unsigned __int64)
0x14001b011  test    eax, eax
0x14001b013  jns     short loc_14001B020
0x14001b015  mov     r9d, 4Bh ; 'K'
0x14001b01b  jmp     loc_14001B24F
0x14001b020  mov     [rsp+40h+var_18], 0; unsigned __int16 *
0x14001b029  xor     r9d, r9d; unsigned __int16 *
0x14001b02c  mov     r8, rsi; unsigned __int16 *
0x14001b02f  lea     rdx, aFinalsubtext; "finalSubtext"
0x14001b036  mov     rcx, rdi; this
0x14001b039  call    ?SetNamedValues@WizardPage@@IEAAJPEBG0000@Z; WizardPage::SetNamedValues(ushort const *,ushort const *,ushort const *,ushort const *,ushort const *)
0x14001b03e  test    eax, eax
0x14001b040  jns     short loc_14001B04D
0x14001b042  mov     r9d, 4Eh ; 'N'
0x14001b048  jmp     loc_14001B24F
0x14001b04d  mov     rax, [rdi]
0x14001b050  lea     rdx, [rbp+arg_8]
0x14001b054  mov     rcx, rdi
0x14001b057  mov     rax, [rax+38h]
0x14001b05b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001b060  test    eax, eax
0x14001b062  jns     short loc_14001B06F
0x14001b064  mov     r9d, 52h ; 'R'
0x14001b06a  jmp     loc_14001B24F
0x14001b06f  mov     rax, [rdi]
0x14001b072  mov     rcx, rdi
0x14001b075  mov     rax, [rax+118h]
0x14001b07c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001b081  test    eax, eax
0x14001b083  jz      loc_14001B11A
0x14001b089  test    rsi, rsi
0x14001b08c  jnz     short loc_14001B0C7
0x14001b08e  call    cs:__imp_GetProcessHeap
0x14001b095  nop     dword ptr [rax+rax+00h]
0x14001b09a  mov     rcx, rax; hHeap
0x14001b09d  mov     r8, rbx; dwBytes
0x14001b0a0  xor     edx, edx; dwFlags
0x14001b0a2  call    cs:__imp_HeapAlloc
0x14001b0a9  nop     dword ptr [rax+rax+00h]
0x14001b0ae  mov     rsi, rax
0x14001b0b1  test    rax, rax
0x14001b0b4  jnz     short loc_14001B0C7
0x14001b0b6  mov     dword ptr [rsp+40h+var_20], 8007000Eh
0x14001b0be  lea     r9d, [rax+59h]
0x14001b0c2  jmp     loc_14001B253
0x14001b0c7  mov     r8d, 400h; cchBufferMax
0x14001b0cd  mov     rdx, rsi; lpBuffer
0x14001b0d0  mov     ecx, 284Bh; uID
0x14001b0d5  call    ?DwzLoadLocalString@@YAJIPEAG_K@Z; DwzLoadLocalString(uint,ushort *,unsigned __int64)
0x14001b0da  test    eax, eax
0x14001b0dc  jns     short loc_14001B0E9
0x14001b0de  mov     r9d, 5Dh ; ']'
0x14001b0e4  jmp     loc_14001B24F
0x14001b0e9  mov     [rsp+40h+var_18], 0; unsigned __int16 *
0x14001b0f2  xor     r9d, r9d; unsigned __int16 *
0x14001b0f5  mov     r8, rsi; unsigned __int16 *
0x14001b0f8  lea     rdx, aFeedbackquesti_0; "feedbackQuestion"
0x14001b0ff  mov     rcx, rdi; this
0x14001b102  call    ?SetNamedValues@WizardPage@@IEAAJPEBG0000@Z; WizardPage::SetNamedValues(ushort const *,ushort const *,ushort const *,ushort const *,ushort const *)
0x14001b107  test    eax, eax
0x14001b109  jns     loc_14001B1AF
0x14001b10f  mov     r9d, 60h ; '`'
0x14001b115  jmp     loc_14001B24F
0x14001b11a  lea     rdx, aFeedbackquesti_0; "feedbackQuestion"
0x14001b121  mov     rcx, rdi; this
0x14001b124  call    ?HideNamedElement@WizardPage@@IEAAJPEBG@Z; WizardPage::HideNamedElement(ushort const *)
0x14001b129  test    eax, eax
0x14001b12b  jns     short loc_14001B138
0x14001b12d  mov     r9d, 65h ; 'e'
0x14001b133  jmp     loc_14001B24F
0x14001b138  lea     rdx, aBtnyes; "btnYes"
0x14001b13f  mov     rcx, rdi; this
0x14001b142  call    ?HideNamedElement@WizardPage@@IEAAJPEBG@Z; WizardPage::HideNamedElement(ushort const *)
0x14001b147  test    eax, eax
0x14001b149  jns     short loc_14001B156
0x14001b14b  mov     r9d, 69h ; 'i'
0x14001b151  jmp     loc_14001B24F
0x14001b156  lea     rdx, aBtnno; "btnNo"
0x14001b15d  mov     rcx, rdi; this
0x14001b160  call    ?HideNamedElement@WizardPage@@IEAAJPEBG@Z; WizardPage::HideNamedElement(ushort const *)
0x14001b165  test    eax, eax
0x14001b167  jns     short loc_14001B174
0x14001b169  mov     r9d, 6Bh ; 'k'
0x14001b16f  jmp     loc_14001B24F
0x14001b174  lea     r9, aNofeedbackques; "nofeedbackQuestionLinks"
0x14001b17b  mov     r8b, r15b; bool
0x14001b17e  mov     rdx, [rbp+arg_8]; struct DirectUI::DUIXmlParser *
0x14001b182  mov     rcx, rdi; this
0x14001b185  call    ?CreateLinks@FinalLinksPage@@IEAAJPEAVDUIXmlParser@DirectUI@@_NPEBG@Z; FinalLinksPage::CreateLinks(DirectUI::DUIXmlParser *,bool,ushort const *)
0x14001b18a  test    eax, eax
0x14001b18c  jns     short loc_14001B1AF
0x14001b18e  lea     r9, aNofeedbackques; "nofeedbackQuestionLinks"
0x14001b195  mov     r8b, r15b; bool
0x14001b198  mov     rdx, [rbp+arg_8]; struct DirectUI::DUIXmlParser *
0x14001b19c  mov     rcx, rdi; this
0x14001b19f  call    ?CreateLinks@FinalLinksPage@@IEAAJPEAVDUIXmlParser@DirectUI@@_NPEBG@Z; FinalLinksPage::CreateLinks(DirectUI::DUIXmlParser *,bool,ushort const *)
0x14001b1a4  mov     r9d, 6Eh ; 'n'
0x14001b1aa  jmp     loc_14001B24F
0x14001b1af  mov     rbx, [rdi+40h]
0x14001b1b3  lea     rcx, aLinkelevate; "linkElevate"
0x14001b1ba  call    cs:__imp_StrToID
0x14001b1c1  nop     dword ptr [rax+rax+00h]
0x14001b1c6  movzx   edx, ax
0x14001b1c9  mov     rcx, rbx
0x14001b1cc  call    cs:__imp_?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z; DirectUI::Element::FindDescendent(ushort)
0x14001b1d3  nop     dword ptr [rax+rax+00h]
0x14001b1d8  mov     rdx, rax
0x14001b1db  test    rax, rax
0x14001b1de  jz      short loc_14001B20C
0x14001b1e0  mov     rcx, [rax]
0x14001b1e3  mov     rax, [rcx+168h]
0x14001b1ea  mov     rcx, rdx
0x14001b1ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001b1f2  mov     r9, r15; lParam
0x14001b1f5  xor     r8d, r8d; wParam
0x14001b1f8  mov     edx, 160Ch; Msg
0x14001b1fd  mov     rcx, rax; hWnd
0x14001b200  call    cs:__imp_SendMessageW
0x14001b207  nop     dword ptr [rax+rax+00h]
0x14001b20c  lea     rcx, [rbp+IsMember]; IsMember
0x14001b210  call    ?IsAdminToken@@YAJPEAH@Z; IsAdminToken(int *)
0x14001b215  test    eax, eax
0x14001b217  jns     short loc_14001B221
0x14001b219  mov     r9d, 78h ; 'x'
0x14001b21f  jmp     short loc_14001B24F
0x14001b221  mov     rax, cs:?Config@@3PEAVConfiguration@@EA; Configuration * Config
0x14001b228  mov     dword ptr [rax+0C4h], 2
0x14001b232  mov     dword ptr [rax+2Ch], 0
0x14001b239  mov     rdx, [rbp+arg_8]; struct DirectUI::DUIXmlParser *
0x14001b23d  mov     rcx, rdi; this
0x14001b240  call    ?AddRootCauses@FinalLinksPage@@IEAAJPEAVDUIXmlParser@DirectUI@@@Z; FinalLinksPage::AddRootCauses(DirectUI::DUIXmlParser *)
0x14001b245  test    eax, eax
0x14001b247  jns     short loc_14001B269
0x14001b249  mov     r9d, 88h
0x14001b24f  mov     dword ptr [rsp+40h+var_20], eax
0x14001b253  lea     r8, aFinallinkspage_2; "FinalLinksPage::OnSetActive"
0x14001b25a  lea     rdx, aDwzErrorSDHr0x; "Dwz ERROR: %s:%d - hr = 0x%08X\n"
0x14001b261  mov     ecx, r15d; Level
0x14001b264  call    ?SdpDebugPrint@@YAXKPEBDZZ; SdpDebugPrint(ulong,char const *,...)
0x14001b269  mov     rcx, [rbp+arg_8]
0x14001b26d  test    rcx, rcx
0x14001b270  jz      short loc_14001B286
0x14001b272  call    cs:__imp_?Destroy@DUIXmlParser@DirectUI@@QEAAXXZ; DirectUI::DUIXmlParser::Destroy(void)
0x14001b279  nop     dword ptr [rax+rax+00h]
0x14001b27e  mov     [rbp+arg_8], 0
0x14001b286  test    rsi, rsi
0x14001b289  jz      short loc_14001B2AC
0x14001b28b  call    cs:__imp_GetProcessHeap
0x14001b292  nop     dword ptr [rax+rax+00h]
0x14001b297  mov     rcx, rax; hHeap
0x14001b29a  mov     r8, rsi; lpMem
0x14001b29d  xor     edx, edx; dwFlags
0x14001b29f  call    cs:__imp_HeapFree
0x14001b2a6  nop     dword ptr [rax+rax+00h]
0x14001b2ab  nop
0x14001b2ac  mov     edx, [rbp+var_8]
0x14001b2af  test    edx, edx
0x14001b2b1  jz      short loc_14001B2C4
0x14001b2b3  mov     rcx, [rbp+var_10]
0x14001b2b7  call    cs:__imp_?EndDefer@Element@DirectUI@@QEAAXK@Z; DirectUI::Element::EndDefer(ulong)
0x14001b2be  nop     dword ptr [rax+rax+00h]
0x14001b2c3  nop
0x14001b2c4  xor     eax, eax
0x14001b2c6  mov     rbx, [rsp+40h+arg_10]
0x14001b2cb  mov     rsi, [rsp+40h+arg_18]
0x14001b2d0  add     rsp, 40h
0x14001b2d4  pop     r15
0x14001b2d6  pop     rdi
0x14001b2d7  pop     rbp
0x14001b2d8  retn
```
