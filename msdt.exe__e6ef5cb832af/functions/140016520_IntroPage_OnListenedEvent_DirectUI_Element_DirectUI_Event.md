# IntroPage::OnListenedEvent(DirectUI::Element *,DirectUI::Event *)

- ea: `0x140016520`
- end: `0x140016a9e`
- name: `?OnListenedEvent@IntroPage@@MEAAXPEAVElement@DirectUI@@PEAUEvent@3@@Z`
- size: `1406`
- prototype: `void __fastcall(IntroPage *__hidden this, struct DirectUI::Element *, struct DirectUI::Event *)`
- caller_count: `0`
- callee_count: `16`
- tags: `registry_config, service_task`

## callees

- `0x1400039b1`
- `0x14000dd7c`
- `0x14000e6bc`
- `0x14000e72c`
- `0x14000e978`
- `0x14000eb84`
- `0x14000f0e0`
- `0x1400108b0`
- `0x140016520`
- `0x140020420`
- `0x14002840c`
- `0x14004175c`
- `0x140049770`
- `0x14004a8d8`
- `0x14004d074`
- `0x140063010`

## import_xrefs

- `USER32!SendMessageW` at `0x1400169e3`
- `USER32!SendMessageW` at `0x140016a0e`
- `USER32!SendMessageW` at `0x1400169e3`
- `USER32!SendMessageW` at `0x140016a0e`
- `OLEAUT32!__imp_SysFreeString` at `0x140016800`
- `OLEAUT32!__imp_SysFreeString` at `0x140016a61`
- `OLEAUT32!__imp_SysFreeString` at `0x140016800`
- `OLEAUT32!__imp_SysFreeString` at `0x140016a61`
- `DUI70!?EndDefer@Element@DirectUI@@QEAAXK@Z` at `0x140016a79`
- `DUI70!?EndDefer@Element@DirectUI@@QEAAXK@Z` at `0x140016a79`
- `DUI70!?StartDefer@Element@DirectUI@@QEAAXPEAK@Z` at `0x14001657a`
- `DUI70!?StartDefer@Element@DirectUI@@QEAAXPEAK@Z` at `0x14001657a`
- `DUI70!?PropSheet_SendMessage@TaskPage@DirectUI@@IEAA_JI_K_J@Z` at `0x14001688b`
- `DUI70!?PropSheet_SendMessage@TaskPage@DirectUI@@IEAA_JI_K_J@Z` at `0x14001688b`
- `DUI70!?Click@Button@DirectUI@@SA?AVUID@@XZ` at `0x140016595`

## string_xrefs

- `0x14001665e`: `advancedlinkpane`
- `0x140016960`: `advancedlinkpane`
- `0x1400165b9`: `linkPrivacy`
- `0x14001661e`: `linkAdvanced`
- `0x1400166f0`: `linkAdmin`
- `0x140016815`: `linkAdmin`
- `0x1400168b4`: `linkPrivacyPublisher`

## pseudocode

```c
void __fastcall IntroPage::OnListenedEvent(IntroPage *this, struct DirectUI::Element *a2, struct DirectUI::Event *a3)
{
  int NamedElement; // eax
  WizardPage *v7; // rcx
  int v8; // r9d
  OLECHAR *v9; // r15
  OLECHAR *v10; // r14
  int v11; // eax
  int v12; // eax
  int v13; // r9d
  int v14; // eax
  WizardPage *v15; // rcx
  int v16; // eax
  __int64 v17; // [rsp+30h] [rbp-49h] BYREF
  DirectUI::Element *v18; // [rsp+38h] [rbp-41h]
  unsigned int v19[4]; // [rsp+40h] [rbp-39h] BYREF
  _DWORD lParam[32]; // [rsp+50h] [rbp-29h] BYREF
  WINBOOL IsMember; // [rsp+E0h] [rbp+67h] BYREF
  struct DirectUI::Element *v22; // [rsp+F0h] [rbp+77h] BYREF
  HWND hWnd; // [rsp+F8h] [rbp+7Fh] BYREF

  v22 = 0;
  IsMember = 0;
  hWnd = 0;
  memset_0(lParam, 0, 0x58u);
  v18 = (DirectUI::Element *)*((_QWORD *)this + 8);
  v19[0] = 0;
  DirectUI::Element::StartDefer(v18, v19);
  WizardPage::OnListenedEvent(this, a2, a3);
  v17 = DirectUI::Button::Click;
  if ( !(unsigned __int8)operator==((char *)a3 + 8, &v17) )
    goto LABEL_77;
  NamedElement = WizardPage::GetNamedElement(this, L"linkPrivacy", &v22);
  if ( NamedElement < 0 )
  {
    v8 = 145;
LABEL_4:
    SdpDebugPrint(1u, "Dwz ERROR: %s:%d - hr = 0x%08X\n", "IntroPage::OnListenedEvent", v8, NamedElement);
    goto LABEL_77;
  }
  if ( *(struct DirectUI::Element **)a3 == v22 )
  {
    NamedElement = WizardPage::LaunchPrivacyLink(v7, 0);
    if ( NamedElement < 0 )
    {
      v8 = 149;
      goto LABEL_4;
    }
    goto LABEL_51;
  }
  NamedElement = WizardPage::GetNamedElement(this, L"linkAdvanced", &v22);
  if ( NamedElement < 0 )
  {
    v8 = 159;
    goto LABEL_4;
  }
  v9 = 0;
  if ( *(struct DirectUI::Element **)a3 == v22 )
  {
    NamedElement = IsAdminToken(&IsMember);
    if ( NamedElement < 0 )
    {
      v8 = 163;
      goto LABEL_4;
    }
    NamedElement = WizardPage::HideNamedElement(this, L"advancedlinkpane");
    if ( NamedElement < 0 )
    {
      v8 = 169;
      goto LABEL_4;
    }
    NamedElement = WizardPage::ShowNamedElement(this, L"advancedpane", 1);
    if ( NamedElement < 0 )
    {
      v8 = 172;
      goto LABEL_4;
    }
    NamedElement = WizardPage::HideNamedElement(this, L"packageList");
    if ( NamedElement < 0 )
    {
      v8 = 175;
      goto LABEL_4;
    }
    NamedElement = WizardPage::GetNamedElement(this, L"cbAuto", &v22);
    if ( NamedElement < 0 )
    {
      v8 = 178;
      goto LABEL_4;
    }
    if ( IsMember || *(_DWORD *)Config )
    {
      NamedElement = WizardPage::HideNamedElement(this, L"adminpane");
      if ( NamedElement < 0 )
      {
        v8 = 186;
        goto LABEL_4;
      }
    }
    else
    {
      NamedElement = WizardPage::GetNamedElement(this, L"linkAdmin", &v22);
      if ( NamedElement < 0 )
      {
        v8 = 189;
        goto LABEL_4;
      }
    }
    v10 = Packages_Publisher();
    if ( v10 )
    {
      v11 = WizardPage::ShowNamedElement(this, L"publisherPane", 1);
      if ( v11 < 0 )
      {
        SdpDebugPrint(1u, "Dwz ERROR: %s:%d - hr = 0x%08X\n", "IntroPage::OnListenedEvent", 196, v11);
LABEL_39:
        SysFreeString(v10);
LABEL_75:
        if ( v9 )
          SysFreeString(v9);
        goto LABEL_77;
      }
    }
    if ( Packages_GetNumber() > 1 && *((_DWORD *)Config + 66) == 6 )
    {
      v12 = WizardPage::ShowNamedElement(this, L"privacyPublisherPane", 1);
      if ( v12 < 0 )
      {
        v13 = 202;
LABEL_34:
        SdpDebugPrint(1u, "Dwz ERROR: %s:%d - hr = 0x%08X\n", "IntroPage::OnListenedEvent", v13, v12);
        goto LABEL_38;
      }
      v12 = WizardPage::HideNamedElement(this, L"publisherPane");
      if ( v12 < 0 )
      {
        v13 = 205;
        goto LABEL_34;
      }
    }
    (*(void (__fastcall **)(struct DirectUI::Element *))(*(_QWORD *)v22 + 168LL))(v22);
    *((_BYTE *)a3 + 16) = 1;
LABEL_38:
    if ( !v10 )
      goto LABEL_75;
    goto LABEL_39;
  }
  NamedElement = WizardPage::GetNamedElement(this, L"linkAdmin", &v22);
  if ( NamedElement < 0 )
  {
    v8 = 218;
    goto LABEL_4;
  }
  if ( *(struct DirectUI::Element **)a3 == v22 )
  {
    NamedElement = IsAdminToken(&IsMember);
    if ( NamedElement < 0 )
    {
      v8 = 222;
      goto LABEL_4;
    }
    if ( !IsMember && !*(_DWORD *)Config )
    {
      NamedElement = Mode::Elevate();
      if ( NamedElement < 0 )
      {
        v8 = 226;
        goto LABEL_4;
      }
      if ( !NamedElement )
      {
        DirectUI::TaskPage::PropSheet_SendMessage(this, 0x471u, 5u, 0);
        *((_DWORD *)Config + 49) = 4;
      }
    }
    goto LABEL_51;
  }
  NamedElement = WizardPage::GetNamedElement(this, L"linkPrivacyPublisher", &v22);
  if ( NamedElement < 0 )
  {
    v8 = 246;
    goto LABEL_4;
  }
  if ( *(struct DirectUI::Element **)a3 == v22 )
  {
    NamedElement = WizardPage::HideNamedElement(this, L"publisherPane");
    if ( NamedElement < 0 )
    {
      v8 = 250;
      goto LABEL_4;
    }
    NamedElement = WizardPage::HideNamedElement(this, L"privacyPublisherPane");
    if ( NamedElement < 0 )
    {
      v8 = 253;
      goto LABEL_4;
    }
    NamedElement = WizardPage::HideNamedElement(this, L"advancedpane");
    if ( NamedElement < 0 )
    {
      v8 = 256;
      goto LABEL_4;
    }
    NamedElement = WizardPage::ShowNamedElement(this, L"packageList", 4);
    if ( NamedElement < 0 )
    {
      v8 = 259;
      goto LABEL_4;
    }
    NamedElement = WizardPage::ShowNamedElement(this, L"advancedlinkpane", 1);
    if ( NamedElement < 0 )
    {
      v8 = 262;
      goto LABEL_4;
    }
LABEL_51:
    *((_BYTE *)a3 + 16) = 1;
    goto LABEL_77;
  }
  NamedElement = WizardPage::GetNamedElement(this, L"btnPrivacy", &v22);
  if ( NamedElement < 0 )
  {
    v8 = 269;
    goto LABEL_4;
  }
  if ( *(struct DirectUI::Element **)a3 == v22 )
  {
    NamedElement = WizardPage::GetNamedHandle(this, L"lstView", &hWnd);
    if ( NamedElement < 0 )
    {
      v8 = 273;
      goto LABEL_4;
    }
    v14 = SendMessageW(hWnd, 0x100Cu, 0xFFFFFFFFFFFFFFFFuLL, 2);
    if ( v14 == -1
      || (lParam[1] = v14, lParam[0] = 4, !(unsigned int)SendMessageW(hWnd, 0x104Bu, 0, (LPARAM)lParam))
      || (v9 = Package_PrivacyLink(lParam[10]), v16 = WizardPage::LaunchPrivacyLink(v15, v9), v16 >= 0) )
    {
      *((_BYTE *)a3 + 16) = 1;
    }
    else
    {
      SdpDebugPrint(1u, "Dwz ERROR: %s:%d - hr = 0x%08X\n", "IntroPage::OnListenedEvent", 287, v16);
    }
    goto LABEL_75;
  }
LABEL_77:
  if ( v19[0] )
    DirectUI::Element::EndDefer(v18, v19[0]);
}

```

## disassembly

```asm
0x140016520  mov     [rsp-8+arg_8], rbx
0x140016525  push    rbp
0x140016526  push    rsi
0x140016527  push    rdi
0x140016528  push    r14
0x14001652a  push    r15
0x14001652c  lea     rbp, [rsp-37h]
0x140016531  sub     rsp, 0B0h
0x140016538  mov     rsi, r8
0x14001653b  mov     rbx, rdx
0x14001653e  mov     rdi, rcx
0x140016541  mov     [rbp+57h+arg_10], 0
0x140016549  mov     [rbp+57h+IsMember], 0
0x140016550  mov     [rbp+57h+hWnd], 0
0x140016558  xor     edx, edx; Val
0x14001655a  lea     r8d, [rdx+58h]; Size
0x14001655e  lea     rcx, [rbp+57h+lParam]; void *
0x140016562  call    memset_0
0x140016567  mov     rcx, [rdi+40h]
0x14001656b  mov     [rbp+57h+var_98], rcx
0x14001656f  mov     [rbp+57h+var_90], 0
0x140016576  lea     rdx, [rbp+57h+var_90]
0x14001657a  call    cs:__imp_?StartDefer@Element@DirectUI@@QEAAXPEAK@Z; DirectUI::Element::StartDefer(ulong *)
0x140016581  nop     dword ptr [rax+rax+00h]
0x140016586  nop
0x140016587  mov     r8, rsi; struct DirectUI::Event *
0x14001658a  mov     rdx, rbx; struct DirectUI::Element *
0x14001658d  mov     rcx, rdi; this
0x140016590  call    ?OnListenedEvent@WizardPage@@UEAAXPEAVElement@DirectUI@@PEAUEvent@3@@Z; WizardPage::OnListenedEvent(DirectUI::Element *,DirectUI::Event *)
0x140016595  mov     rax, cs:__imp_?Click@Button@DirectUI@@SA?AVUID@@XZ; DirectUI::Button::Click(void)
0x14001659c  mov     [rbp+57h+var_A0], rax
0x1400165a0  lea     rcx, [rsi+8]
0x1400165a4  lea     rdx, [rbp+57h+var_A0]
0x1400165a8  call    ??8@YA_NAEBVUID@@AEBQ6A?AV0@XZ@Z; operator==(UID const &,UID (*const &)(void))
0x1400165ad  test    al, al
0x1400165af  jz      loc_140016A6E
0x1400165b5  lea     r8, [rbp+57h+arg_10]; struct DirectUI::Element **
0x1400165b9  lea     rdx, aLinkprivacy; "linkPrivacy"
0x1400165c0  mov     rcx, rdi; this
0x1400165c3  call    ?GetNamedElement@WizardPage@@QEAAJPEBGPEAPEAVElement@DirectUI@@@Z; WizardPage::GetNamedElement(ushort const *,DirectUI::Element * *)
0x1400165c8  test    eax, eax
0x1400165ca  jns     short loc_1400165F3
0x1400165cc  mov     r9d, 91h
0x1400165d2  mov     ecx, 1; Level
0x1400165d7  mov     [rsp+0D0h+var_B0], eax
0x1400165db  lea     rdx, aDwzErrorSDHr0x; "Dwz ERROR: %s:%d - hr = 0x%08X\n"
0x1400165e2  lea     r8, aIntropageOnlis; "IntroPage::OnListenedEvent"
0x1400165e9  call    ?SdpDebugPrint@@YAXKPEBDZZ; SdpDebugPrint(ulong,char const *,...)
0x1400165ee  jmp     loc_140016A6E
0x1400165f3  mov     ebx, 1
0x1400165f8  mov     rax, [rbp+57h+arg_10]
0x1400165fc  cmp     [rsi], rax
0x1400165ff  jnz     short loc_14001661A
0x140016601  xor     edx, edx; unsigned __int16 *
0x140016603  call    ?LaunchPrivacyLink@WizardPage@@QEAAJPEBG@Z; WizardPage::LaunchPrivacyLink(ushort const *)
0x140016608  test    eax, eax
0x14001660a  jns     loc_1400168A8
0x140016610  mov     r9d, 95h
0x140016616  mov     ecx, ebx
0x140016618  jmp     short loc_1400165D7
0x14001661a  lea     r8, [rbp+57h+arg_10]; struct DirectUI::Element **
0x14001661e  lea     rdx, aLinkadvanced; "linkAdvanced"
0x140016625  mov     rcx, rdi; this
0x140016628  call    ?GetNamedElement@WizardPage@@QEAAJPEBGPEAPEAVElement@DirectUI@@@Z; WizardPage::GetNamedElement(ushort const *,DirectUI::Element * *)
0x14001662d  test    eax, eax
0x14001662f  jns     short loc_140016639
0x140016631  mov     r9d, 9Fh
0x140016637  jmp     short loc_140016616
0x140016639  xor     r15d, r15d
0x14001663c  mov     rax, [rbp+57h+arg_10]
0x140016640  cmp     [rsi], rax
0x140016643  jnz     loc_140016811
0x140016649  lea     rcx, [rbp+57h+IsMember]; IsMember
0x14001664d  call    ?IsAdminToken@@YAJPEAH@Z; IsAdminToken(int *)
0x140016652  test    eax, eax
0x140016654  jns     short loc_14001665E
0x140016656  mov     r9d, 0A3h
0x14001665c  jmp     short loc_140016616
0x14001665e  lea     rdx, aAdvancedlinkpa; "advancedlinkpane"
0x140016665  mov     rcx, rdi; this
0x140016668  call    ?HideNamedElement@WizardPage@@IEAAJPEBG@Z; WizardPage::HideNamedElement(ushort const *)
0x14001666d  test    eax, eax
0x14001666f  jns     short loc_140016679
0x140016671  mov     r9d, 0A9h
0x140016677  jmp     short loc_140016616
0x140016679  mov     r8d, ebx; int
0x14001667c  lea     rdx, aAdvancedpane; "advancedpane"
0x140016683  mov     rcx, rdi; this
0x140016686  call    ?ShowNamedElement@WizardPage@@IEAAJPEBGH@Z; WizardPage::ShowNamedElement(ushort const *,int)
0x14001668b  test    eax, eax
0x14001668d  jns     short loc_14001669A
0x14001668f  mov     r9d, 0ACh
0x140016695  jmp     loc_140016616
0x14001669a  lea     rdx, aPackagelist; "packageList"
0x1400166a1  mov     rcx, rdi; this
0x1400166a4  call    ?HideNamedElement@WizardPage@@IEAAJPEBG@Z; WizardPage::HideNamedElement(ushort const *)
0x1400166a9  test    eax, eax
0x1400166ab  jns     short loc_1400166B8
0x1400166ad  mov     r9d, 0AFh
0x1400166b3  jmp     loc_140016616
0x1400166b8  lea     r8, [rbp+57h+arg_10]; struct DirectUI::Element **
0x1400166bc  lea     rdx, aCbauto; "cbAuto"
0x1400166c3  mov     rcx, rdi; this
0x1400166c6  call    ?GetNamedElement@WizardPage@@QEAAJPEBGPEAPEAVElement@DirectUI@@@Z; WizardPage::GetNamedElement(ushort const *,DirectUI::Element * *)
0x1400166cb  test    eax, eax
0x1400166cd  jns     short loc_1400166DA
0x1400166cf  mov     r9d, 0B2h
0x1400166d5  jmp     loc_140016616
0x1400166da  cmp     [rbp+57h+IsMember], r15d
0x1400166de  jnz     short loc_14001670E
0x1400166e0  mov     rax, cs:?Config@@3PEAVConfiguration@@EA; Configuration * Config
0x1400166e7  cmp     [rax], r15d
0x1400166ea  jnz     short loc_14001670E
0x1400166ec  lea     r8, [rbp+57h+arg_10]; struct DirectUI::Element **
0x1400166f0  lea     rdx, aLinkadmin; "linkAdmin"
0x1400166f7  mov     rcx, rdi; this
0x1400166fa  call    ?GetNamedElement@WizardPage@@QEAAJPEBGPEAPEAVElement@DirectUI@@@Z; WizardPage::GetNamedElement(ushort const *,DirectUI::Element * *)
0x1400166ff  test    eax, eax
0x140016701  jns     short loc_14001672C
0x140016703  mov     r9d, 0BDh
0x140016709  jmp     loc_140016616
0x14001670e  lea     rdx, aAdminpane; "adminpane"
0x140016715  mov     rcx, rdi; this
0x140016718  call    ?HideNamedElement@WizardPage@@IEAAJPEBG@Z; WizardPage::HideNamedElement(ushort const *)
0x14001671d  test    eax, eax
0x14001671f  jns     short loc_14001672C
0x140016721  mov     r9d, 0BAh
0x140016727  jmp     loc_140016616
0x14001672c  call    ?Packages_Publisher@@YAPEAGXZ; Packages_Publisher(void)
0x140016731  mov     r14, rax
0x140016734  test    rax, rax
0x140016737  jz      short loc_140016773
0x140016739  mov     r8d, ebx; int
0x14001673c  lea     rdx, aPublisherpane; "publisherPane"
0x140016743  mov     rcx, rdi; this
0x140016746  call    ?ShowNamedElement@WizardPage@@IEAAJPEBGH@Z; WizardPage::ShowNamedElement(ushort const *,int)
0x14001674b  test    eax, eax
0x14001674d  jns     short loc_140016773
0x14001674f  mov     [rsp+0D0h+var_B0], eax
0x140016753  mov     r9d, 0C4h
0x140016759  lea     r8, aIntropageOnlis; "IntroPage::OnListenedEvent"
0x140016760  lea     rdx, aDwzErrorSDHr0x; "Dwz ERROR: %s:%d - hr = 0x%08X\n"
0x140016767  mov     ecx, ebx; Level
0x140016769  call    ?SdpDebugPrint@@YAXKPEBDZZ; SdpDebugPrint(ulong,char const *,...)
0x14001676e  jmp     loc_1400167FD
0x140016773  call    ?Packages_GetNumber@@YAIXZ; Packages_GetNumber(void)
0x140016778  cmp     eax, ebx
0x14001677a  jbe     short loc_1400167DE
0x14001677c  mov     rax, cs:?Config@@3PEAVConfiguration@@EA; Configuration * Config
0x140016783  cmp     dword ptr [rax+108h], 6
0x14001678a  jnz     short loc_1400167DE
0x14001678c  mov     r8d, ebx; int
0x14001678f  lea     rdx, aPrivacypublish; "privacyPublisherPane"
0x140016796  mov     rcx, rdi; this
0x140016799  call    ?ShowNamedElement@WizardPage@@IEAAJPEBGH@Z; WizardPage::ShowNamedElement(ushort const *,int)
0x14001679e  test    eax, eax
0x1400167a0  jns     short loc_1400167C3
0x1400167a2  mov     r9d, 0CAh
0x1400167a8  mov     [rsp+0D0h+var_B0], eax
0x1400167ac  lea     r8, aIntropageOnlis; "IntroPage::OnListenedEvent"
0x1400167b3  lea     rdx, aDwzErrorSDHr0x; "Dwz ERROR: %s:%d - hr = 0x%08X\n"
0x1400167ba  mov     ecx, ebx; Level
0x1400167bc  call    ?SdpDebugPrint@@YAXKPEBDZZ; SdpDebugPrint(ulong,char const *,...)
0x1400167c1  jmp     short loc_1400167F4
0x1400167c3  lea     rdx, aPublisherpane; "publisherPane"
0x1400167ca  mov     rcx, rdi; this
0x1400167cd  call    ?HideNamedElement@WizardPage@@IEAAJPEBG@Z; WizardPage::HideNamedElement(ushort const *)
0x1400167d2  test    eax, eax
0x1400167d4  jns     short loc_1400167DE
0x1400167d6  mov     r9d, 0CDh
0x1400167dc  jmp     short loc_1400167A8
0x1400167de  mov     rcx, [rbp+57h+arg_10]
0x1400167e2  mov     rax, [rcx]
0x1400167e5  mov     rax, [rax+0A8h]
0x1400167ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400167f1  mov     [rsi+10h], bl
0x1400167f4  test    r14, r14
0x1400167f7  jz      loc_140016A59
0x1400167fd  mov     rcx, r14; bstrString
0x140016800  call    cs:__imp_SysFreeString
0x140016807  nop     dword ptr [rax+rax+00h]
0x14001680c  jmp     loc_140016A59
0x140016811  lea     r8, [rbp+57h+arg_10]; struct DirectUI::Element **
0x140016815  lea     rdx, aLinkadmin; "linkAdmin"
0x14001681c  mov     rcx, rdi; this
0x14001681f  call    ?GetNamedElement@WizardPage@@QEAAJPEBGPEAPEAVElement@DirectUI@@@Z; WizardPage::GetNamedElement(ushort const *,DirectUI::Element * *)
0x140016824  test    eax, eax
0x140016826  jns     short loc_140016833
0x140016828  mov     r9d, 0DAh
0x14001682e  jmp     loc_140016616
0x140016833  mov     rax, [rbp+57h+arg_10]
0x140016837  cmp     [rsi], rax
0x14001683a  jnz     short loc_1400168B0
0x14001683c  lea     rcx, [rbp+57h+IsMember]; IsMember
0x140016840  call    ?IsAdminToken@@YAJPEAH@Z; IsAdminToken(int *)
0x140016845  test    eax, eax
0x140016847  jns     short loc_140016854
0x140016849  mov     r9d, 0DEh
0x14001684f  jmp     loc_140016616
0x140016854  cmp     [rbp+57h+IsMember], r15d
0x140016858  jnz     short loc_1400168A8
0x14001685a  mov     rax, cs:?Config@@3PEAVConfiguration@@EA; Configuration * Config
0x140016861  cmp     [rax], r15d
0x140016864  jnz     short loc_1400168A8
0x140016866  call    ?Elevate@Mode@@SAJXZ; Mode::Elevate(void)
0x14001686b  test    eax, eax
0x14001686d  jns     short loc_14001687A
0x14001686f  mov     r9d, 0E2h
0x140016875  jmp     loc_140016616
0x14001687a  jnz     short loc_1400168A8
0x14001687c  xor     r9d, r9d
0x14001687f  mov     edx, 471h
0x140016884  lea     r8d, [r9+5]
0x140016888  mov     rcx, rdi
0x14001688b  call    cs:__imp_?PropSheet_SendMessage@TaskPage@DirectUI@@IEAA_JI_K_J@Z; DirectUI::TaskPage::PropSheet_SendMessage(uint,unsigned __int64,__int64)
0x140016892  nop     dword ptr [rax+rax+00h]
0x140016897  mov     rax, cs:?Config@@3PEAVConfiguration@@EA; Configuration * Config
0x14001689e  mov     dword ptr [rax+0C4h], 4
0x1400168a8  mov     [rsi+10h], bl
0x1400168ab  jmp     loc_140016A6E
0x1400168b0  lea     r8, [rbp+57h+arg_10]; struct DirectUI::Element **
0x1400168b4  lea     rdx, aLinkprivacypub; "linkPrivacyPublisher"
0x1400168bb  mov     rcx, rdi; this
0x1400168be  call    ?GetNamedElement@WizardPage@@QEAAJPEBGPEAPEAVElement@DirectUI@@@Z; WizardPage::GetNamedElement(ushort const *,DirectUI::Element * *)
0x1400168c3  test    eax, eax
0x1400168c5  jns     short loc_1400168D2
0x1400168c7  mov     r9d, 0F6h
0x1400168cd  jmp     loc_140016616
0x1400168d2  mov     rax, [rbp+57h+arg_10]
0x1400168d6  mov     rcx, rdi; this
0x1400168d9  cmp     [rsi], rax
0x1400168dc  jnz     loc_140016982
0x1400168e2  lea     rdx, aPublisherpane; "publisherPane"
0x1400168e9  call    ?HideNamedElement@WizardPage@@IEAAJPEBG@Z; WizardPage::HideNamedElement(ushort const *)
0x1400168ee  test    eax, eax
0x1400168f0  jns     short loc_1400168FD
0x1400168f2  mov     r9d, 0FAh
0x1400168f8  jmp     loc_140016616
0x1400168fd  lea     rdx, aPrivacypublish; "privacyPublisherPane"
0x140016904  mov     rcx, rdi; this
0x140016907  call    ?HideNamedElement@WizardPage@@IEAAJPEBG@Z; WizardPage::HideNamedElement(ushort const *)
0x14001690c  test    eax, eax
0x14001690e  jns     short loc_14001691B
0x140016910  mov     r9d, 0FDh
0x140016916  jmp     loc_140016616
0x14001691b  lea     rdx, aAdvancedpane; "advancedpane"
0x140016922  mov     rcx, rdi; this
0x140016925  call    ?HideNamedElement@WizardPage@@IEAAJPEBG@Z; WizardPage::HideNamedElement(ushort const *)
0x14001692a  test    eax, eax
0x14001692c  jns     short loc_140016939
0x14001692e  mov     r9d, 100h
0x140016934  jmp     loc_140016616
0x140016939  mov     r8d, 4; int
0x14001693f  lea     rdx, aPackagelist; "packageList"
0x140016946  mov     rcx, rdi; this
0x140016949  call    ?ShowNamedElement@WizardPage@@IEAAJPEBGH@Z; WizardPage::ShowNamedElement(ushort const *,int)
0x14001694e  test    eax, eax
0x140016950  jns     short loc_14001695D
0x140016952  mov     r9d, 103h
0x140016958  jmp     loc_140016616
0x14001695d  mov     r8d, ebx; int
0x140016960  lea     rdx, aAdvancedlinkpa; "advancedlinkpane"
0x140016967  mov     rcx, rdi; this
0x14001696a  call    ?ShowNamedElement@WizardPage@@IEAAJPEBGH@Z; WizardPage::ShowNamedElement(ushort const *,int)
0x14001696f  test    eax, eax
0x140016971  jns     loc_1400168A8
0x140016977  mov     r9d, 106h
0x14001697d  jmp     loc_140016616
0x140016982  lea     r8, [rbp+57h+arg_10]; struct DirectUI::Element **
0x140016986  lea     rdx, aBtnprivacy; "btnPrivacy"
0x14001698d  call    ?GetNamedElement@WizardPage@@QEAAJPEBGPEAPEAVElement@DirectUI@@@Z; WizardPage::GetNamedElement(ushort const *,DirectUI::Element * *)
0x140016992  test    eax, eax
0x140016994  jns     short loc_1400169A1
0x140016996  mov     r9d, 10Dh
0x14001699c  jmp     loc_140016616
0x1400169a1  mov     rax, [rbp+57h+arg_10]
0x1400169a5  cmp     [rsi], rax
0x1400169a8  jnz     loc_140016A6E
0x1400169ae  lea     r8, [rbp+57h+hWnd]; HWND *
0x1400169b2  lea     rdx, aLstview; "lstView"
0x1400169b9  mov     rcx, rdi; this
0x1400169bc  call    ?GetNamedHandle@WizardPage@@IEAAJPEBGPEAPEAUHWND__@@@Z; WizardPage::GetNamedHandle(ushort const *,HWND__ * *)
0x1400169c1  test    eax, eax
0x1400169c3  jns     short loc_1400169D0
0x1400169c5  mov     r9d, 111h
0x1400169cb  jmp     loc_140016616
0x1400169d0  mov     r9d, 2; lParam
0x1400169d6  or      r8, 0FFFFFFFFFFFFFFFFh; wParam
0x1400169da  mov     edx, 100Ch; Msg
0x1400169df  mov     rcx, [rbp+57h+hWnd]; hWnd
0x1400169e3  call    cs:__imp_SendMessageW
0x1400169ea  nop     dword ptr [rax+rax+00h]
0x1400169ef  cmp     eax, 0FFFFFFFFh
0x1400169f2  jz      short loc_140016A56
0x1400169f4  mov     dword ptr [rbp+57h+lParam+4], eax
0x1400169f7  mov     dword ptr [rbp+57h+lParam], 4
0x1400169fe  lea     r9, [rbp+57h+lParam]; lParam
0x140016a02  xor     r8d, r8d; wParam
0x140016a05  mov     edx, 104Bh; Msg
0x140016a0a  mov     rcx, [rbp+57h+hWnd]; hWnd
  ... truncated ...
```
