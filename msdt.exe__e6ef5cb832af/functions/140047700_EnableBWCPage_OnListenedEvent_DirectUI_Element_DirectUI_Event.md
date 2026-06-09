# EnableBWCPage::OnListenedEvent(DirectUI::Element *,DirectUI::Event *)

- ea: `0x140047700`
- end: `0x1400478fa`
- name: `?OnListenedEvent@EnableBWCPage@@MEAAXPEAVElement@DirectUI@@PEAUEvent@3@@Z`
- size: `506`
- prototype: `void __fastcall(EnableBWCPage *__hidden this, struct DirectUI::Element *, struct DirectUI::Event *)`
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x14000dd7c`
- `0x14000e6bc`
- `0x14000eb84`
- `0x14000f0e0`
- `0x140020420`
- `0x140047700`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1400477ac`
- `KERNEL32!GetLastError` at `0x140047818`
- `KERNEL32!GetLastError` at `0x1400477ac`
- `KERNEL32!GetLastError` at `0x140047818`
- `KERNEL32!SetEvent` at `0x140047798`
- `KERNEL32!SetEvent` at `0x140047808`
- `KERNEL32!SetEvent` at `0x140047798`
- `KERNEL32!SetEvent` at `0x140047808`
- `DUI70!?PropSheet_SendMessage@TaskPage@DirectUI@@IEAA_JI_K_J@Z` at `0x14004787f`
- `DUI70!?PropSheet_SendMessage@TaskPage@DirectUI@@IEAA_JI_K_J@Z` at `0x14004787f`
- `DUI70!?Click@Button@DirectUI@@SA?AVUID@@XZ` at `0x140047726`

## string_xrefs

- `0x140047895`: `linkPrivacy`
- `0x140047750`: `cplSettingsLink`
- `0x1400477dc`: `localBWCLink`
- `0x140047847`: `doneLink`
- `0x1400478ba`: `https://go.microsoft.com/fwlink/?LinkId=521839`

## pseudocode

```c
void __fastcall EnableBWCPage::OnListenedEvent(
        EnableBWCPage *this,
        struct DirectUI::Element *a2,
        struct DirectUI::Event *a3)
{
  int NamedElement; // eax
  int v7; // r9d
  bool v8; // sf
  bool v9; // sf
  WizardPage *v10; // rcx
  struct DirectUI::Element *v11; // [rsp+50h] [rbp+18h] BYREF
  __int64 v12; // [rsp+58h] [rbp+20h] BYREF

  v11 = 0;
  WizardPage::OnListenedEvent(this, a2, a3);
  v12 = DirectUI::Button::Click;
  if ( (unsigned __int8)operator==((char *)a3 + 8, &v12) )
  {
    NamedElement = WizardPage::GetNamedElement(this, L"cplSettingsLink", &v11);
    if ( NamedElement < 0 )
    {
      v7 = 155;
LABEL_4:
      SdpDebugPrint(1u, "Dwz ERROR: %s:%d - hr = 0x%08X\n", "EnableBWCPage::OnListenedEvent", v7, NamedElement);
      return;
    }
    if ( *(struct DirectUI::Element **)a3 == v11 )
    {
      if ( !SetEvent(qword_140080060) )
      {
        NamedElement = GetLastError();
        v8 = NamedElement < 0;
        if ( NamedElement > 0 )
        {
          NamedElement = (unsigned __int16)NamedElement | 0x80070000;
          v8 = NamedElement < 0;
        }
        if ( v8 )
        {
          v7 = 159;
          goto LABEL_4;
        }
      }
      goto LABEL_28;
    }
    NamedElement = WizardPage::GetNamedElement(this, L"localBWCLink", &v11);
    if ( NamedElement < 0 )
    {
      v7 = 169;
      goto LABEL_4;
    }
    if ( *(struct DirectUI::Element **)a3 == v11 )
    {
      if ( !SetEvent(qword_140080068) )
      {
        NamedElement = GetLastError();
        v9 = NamedElement < 0;
        if ( NamedElement > 0 )
        {
          NamedElement = (unsigned __int16)NamedElement | 0x80070000;
          v9 = NamedElement < 0;
        }
        if ( v9 )
        {
          v7 = 173;
          goto LABEL_4;
        }
      }
      goto LABEL_22;
    }
    NamedElement = WizardPage::GetNamedElement(this, L"doneLink", &v11);
    if ( NamedElement < 0 )
    {
      v7 = 184;
      goto LABEL_4;
    }
    if ( *(struct DirectUI::Element **)a3 == v11 )
    {
LABEL_22:
      *((_BYTE *)a3 + 16) = 1;
      DirectUI::TaskPage::PropSheet_SendMessage(this, 0x471u, 5u, 0);
      return;
    }
    NamedElement = WizardPage::GetNamedElement(this, L"linkPrivacy", &v11);
    if ( NamedElement < 0 )
    {
      v7 = 196;
      goto LABEL_4;
    }
    if ( *(struct DirectUI::Element **)a3 == v11 )
    {
      NamedElement = WizardPage::LaunchPrivacyLink(v10, L"https://go.microsoft.com/fwlink/?LinkId=521839");
      if ( NamedElement < 0 )
      {
        v7 = 199;
        goto LABEL_4;
      }
LABEL_28:
      *((_BYTE *)a3 + 16) = 1;
      return;
    }
  }
  WizardPage::OnListenedEvent(this, a2, a3);
}

```

## disassembly

```asm
0x140047700  mov     [rsp+arg_0], rbx
0x140047705  mov     [rsp+arg_8], rsi
0x14004770a  push    rdi
0x14004770b  sub     rsp, 30h
0x14004770f  mov     rbx, r8
0x140047712  mov     [rsp+38h+arg_10], 0
0x14004771b  mov     rsi, rdx
0x14004771e  mov     rdi, rcx
0x140047721  call    ?OnListenedEvent@WizardPage@@UEAAXPEAVElement@DirectUI@@PEAUEvent@3@@Z; WizardPage::OnListenedEvent(DirectUI::Element *,DirectUI::Event *)
0x140047726  mov     rax, cs:__imp_?Click@Button@DirectUI@@SA?AVUID@@XZ; DirectUI::Button::Click(void)
0x14004772d  lea     rcx, [rbx+8]
0x140047731  lea     rdx, [rsp+38h+arg_18]
0x140047736  mov     [rsp+38h+arg_18], rax
0x14004773b  call    ??8@YA_NAEBVUID@@AEBQ6A?AV0@XZ@Z; operator==(UID const &,UID (*const &)(void))
0x140047740  test    al, al
0x140047742  jz      loc_1400478DB
0x140047748  lea     r8, [rsp+38h+arg_10]; struct DirectUI::Element **
0x14004774d  mov     rcx, rdi; this
0x140047750  lea     rdx, aCplsettingslin; "cplSettingsLink"
0x140047757  call    ?GetNamedElement@WizardPage@@QEAAJPEBGPEAPEAVElement@DirectUI@@@Z; WizardPage::GetNamedElement(ushort const *,DirectUI::Element * *)
0x14004775c  test    eax, eax
0x14004775e  jns     short loc_140047787
0x140047760  mov     r9d, 9Bh
0x140047766  lea     r8, aEnablebwcpageO_1; "EnableBWCPage::OnListenedEvent"
0x14004776d  mov     [rsp+38h+var_18], eax
0x140047771  lea     rdx, aDwzErrorSDHr0x; "Dwz ERROR: %s:%d - hr = 0x%08X\n"
0x140047778  mov     ecx, 1; Level
0x14004777d  call    ?SdpDebugPrint@@YAXKPEBDZZ; SdpDebugPrint(ulong,char const *,...)
0x140047782  jmp     loc_1400478E9
0x140047787  mov     rax, [rsp+38h+arg_10]
0x14004778c  cmp     [rbx], rax
0x14004778f  jnz     short loc_1400477D4
0x140047791  mov     rcx, cs:qword_140080060; hEvent
0x140047798  call    cs:__imp_SetEvent
0x14004779f  nop     dword ptr [rax+rax+00h]
0x1400477a4  test    eax, eax
0x1400477a6  jnz     loc_1400478D5
0x1400477ac  call    cs:__imp_GetLastError
0x1400477b3  nop     dword ptr [rax+rax+00h]
0x1400477b8  test    eax, eax
0x1400477ba  jle     short loc_1400477C6
0x1400477bc  movzx   eax, ax
0x1400477bf  or      eax, 80070000h
0x1400477c4  test    eax, eax
0x1400477c6  jns     loc_1400478D5
0x1400477cc  mov     r9d, 9Fh
0x1400477d2  jmp     short loc_140047766
0x1400477d4  lea     r8, [rsp+38h+arg_10]; struct DirectUI::Element **
0x1400477d9  mov     rcx, rdi; this
0x1400477dc  lea     rdx, aLocalbwclink; "localBWCLink"
0x1400477e3  call    ?GetNamedElement@WizardPage@@QEAAJPEBGPEAPEAVElement@DirectUI@@@Z; WizardPage::GetNamedElement(ushort const *,DirectUI::Element * *)
0x1400477e8  test    eax, eax
0x1400477ea  jns     short loc_1400477F7
0x1400477ec  mov     r9d, 0A9h
0x1400477f2  jmp     loc_140047766
0x1400477f7  mov     rax, [rsp+38h+arg_10]
0x1400477fc  cmp     [rbx], rax
0x1400477ff  jnz     short loc_14004783F
0x140047801  mov     rcx, cs:qword_140080068; hEvent
0x140047808  call    cs:__imp_SetEvent
0x14004780f  nop     dword ptr [rax+rax+00h]
0x140047814  test    eax, eax
0x140047816  jnz     short loc_14004786C
0x140047818  call    cs:__imp_GetLastError
0x14004781f  nop     dword ptr [rax+rax+00h]
0x140047824  test    eax, eax
0x140047826  jle     short loc_140047832
0x140047828  movzx   eax, ax
0x14004782b  or      eax, 80070000h
0x140047830  test    eax, eax
0x140047832  jns     short loc_14004786C
0x140047834  mov     r9d, 0ADh
0x14004783a  jmp     loc_140047766
0x14004783f  lea     r8, [rsp+38h+arg_10]; struct DirectUI::Element **
0x140047844  mov     rcx, rdi; this
0x140047847  lea     rdx, aDonelink; "doneLink"
0x14004784e  call    ?GetNamedElement@WizardPage@@QEAAJPEBGPEAPEAVElement@DirectUI@@@Z; WizardPage::GetNamedElement(ushort const *,DirectUI::Element * *)
0x140047853  test    eax, eax
0x140047855  jns     short loc_140047862
0x140047857  mov     r9d, 0B8h
0x14004785d  jmp     loc_140047766
0x140047862  mov     rax, [rsp+38h+arg_10]
0x140047867  cmp     [rbx], rax
0x14004786a  jnz     short loc_14004788D
0x14004786c  xor     r9d, r9d
0x14004786f  mov     byte ptr [rbx+10h], 1
0x140047873  mov     edx, 471h
0x140047878  mov     rcx, rdi
0x14004787b  lea     r8d, [r9+5]
0x14004787f  call    cs:__imp_?PropSheet_SendMessage@TaskPage@DirectUI@@IEAA_JI_K_J@Z; DirectUI::TaskPage::PropSheet_SendMessage(uint,unsigned __int64,__int64)
0x140047886  nop     dword ptr [rax+rax+00h]
0x14004788b  jmp     short loc_1400478E9
0x14004788d  lea     r8, [rsp+38h+arg_10]; struct DirectUI::Element **
0x140047892  mov     rcx, rdi; this
0x140047895  lea     rdx, aLinkprivacy; "linkPrivacy"
0x14004789c  call    ?GetNamedElement@WizardPage@@QEAAJPEBGPEAPEAVElement@DirectUI@@@Z; WizardPage::GetNamedElement(ushort const *,DirectUI::Element * *)
0x1400478a1  test    eax, eax
0x1400478a3  jns     short loc_1400478B0
0x1400478a5  mov     r9d, 0C4h
0x1400478ab  jmp     loc_140047766
0x1400478b0  mov     rax, [rsp+38h+arg_10]
0x1400478b5  cmp     [rbx], rax
0x1400478b8  jnz     short loc_1400478DB
0x1400478ba  lea     rdx, aHttpsGoMicroso; "https://go.microsoft.com/fwlink/?LinkId"...
0x1400478c1  call    ?LaunchPrivacyLink@WizardPage@@QEAAJPEBG@Z; WizardPage::LaunchPrivacyLink(ushort const *)
0x1400478c6  test    eax, eax
0x1400478c8  jns     short loc_1400478D5
0x1400478ca  mov     r9d, 0C7h
0x1400478d0  jmp     loc_140047766
0x1400478d5  mov     byte ptr [rbx+10h], 1
0x1400478d9  jmp     short loc_1400478E9
0x1400478db  mov     r8, rbx; struct DirectUI::Event *
0x1400478de  mov     rdx, rsi; struct DirectUI::Element *
0x1400478e1  mov     rcx, rdi; this
0x1400478e4  call    ?OnListenedEvent@WizardPage@@UEAAXPEAVElement@DirectUI@@PEAUEvent@3@@Z; WizardPage::OnListenedEvent(DirectUI::Element *,DirectUI::Event *)
0x1400478e9  mov     rbx, [rsp+38h+arg_0]
0x1400478ee  mov     rsi, [rsp+38h+arg_8]
0x1400478f3  add     rsp, 30h
0x1400478f7  pop     rdi
0x1400478f8  retn
```
