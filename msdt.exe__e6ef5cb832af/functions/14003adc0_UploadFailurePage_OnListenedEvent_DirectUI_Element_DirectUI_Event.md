# UploadFailurePage::OnListenedEvent(DirectUI::Element *,DirectUI::Event *)

- ea: `0x14003adc0`
- end: `0x14003af92`
- name: `?OnListenedEvent@UploadFailurePage@@MEAAXPEAVElement@DirectUI@@PEAUEvent@3@@Z`
- size: `466`
- prototype: `void __fastcall(UploadFailurePage *__hidden this, struct DirectUI::Element *, struct DirectUI::Event *)`
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x1400039b1`
- `0x14000dd7c`
- `0x14000e23c`
- `0x14000e6bc`
- `0x14000f0e0`
- `0x140020420`
- `0x14003adc0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x14003aeb4`
- `KERNEL32!GetLastError` at `0x14003aeb4`
- `SHELL32!ShellExecuteExW` at `0x14003aea4`
- `SHELL32!ShellExecuteExW` at `0x14003aea4`
- `DUI70!?PropSheet_SendMessage@TaskPage@DirectUI@@IEAA_JI_K_J@Z` at `0x14003af1e`
- `DUI70!?PropSheet_SendMessage@TaskPage@DirectUI@@IEAA_JI_K_J@Z` at `0x14003af1e`
- `DUI70!?Click@Button@DirectUI@@SA?AVUID@@XZ` at `0x14003ae02`

## string_xrefs

- `0x14003ae29`: `linkHistory`
- `0x14003aee4`: `linkIgnore`
- `0x14003af45`: `linkRetry`

## pseudocode

```c
void __fastcall UploadFailurePage::OnListenedEvent(
        UploadFailurePage *this,
        struct DirectUI::Element *a2,
        struct DirectUI::Event *a3)
{
  signed int NamedElement; // eax
  int v7; // r9d
  bool v8; // sf
  SHELLEXECUTEINFOW pExecInfo; // [rsp+30h] [rbp-29h] BYREF
  struct DirectUI::Element *v10; // [rsp+D0h] [rbp+77h] BYREF
  __int64 v11; // [rsp+D8h] [rbp+7Fh] BYREF

  v10 = 0;
  memset_0(&pExecInfo, 0, sizeof(pExecInfo));
  WizardPage::OnListenedEvent(this, a2, a3);
  v11 = DirectUI::Button::Click;
  if ( (unsigned __int8)operator==((char *)a3 + 8, &v11) )
  {
    NamedElement = WizardPage::GetNamedElement(this, L"linkHistory", &v10);
    if ( NamedElement < 0 )
    {
      v7 = 698;
LABEL_4:
      SdpDebugPrint(1u, "Dwz ERROR: %s:%d - hr = 0x%08X\n", "UploadFailurePage::OnListenedEvent", v7, NamedElement);
      return;
    }
    if ( *(struct DirectUI::Element **)a3 == v10 )
    {
      pExecInfo.cbSize = 112;
      pExecInfo.lpVerb = L"open";
      pExecInfo.fMask = 1024;
      pExecInfo.lpFile = L"control.exe";
      pExecInfo.lpParameters = L"/name Microsoft.Troubleshooting /page historyPage";
      pExecInfo.nShow = 1;
      if ( !ShellExecuteExW(&pExecInfo) )
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
          v7 = 712;
          goto LABEL_4;
        }
      }
      goto LABEL_15;
    }
    NamedElement = WizardPage::GetNamedElement(this, L"linkIgnore", &v10);
    if ( NamedElement < 0 )
    {
      v7 = 722;
      goto LABEL_4;
    }
    if ( *(struct DirectUI::Element **)a3 == v10 )
    {
      *((_DWORD *)Config + 3) = 1;
      DirectUI::TaskPage::PropSheet_SendMessage(this, 0x471u, 5u, 0);
LABEL_15:
      *((_BYTE *)a3 + 16) = 1;
      return;
    }
    NamedElement = WizardPage::GetNamedElement(this, L"linkRetry", &v10);
    if ( NamedElement < 0 )
    {
      v7 = 737;
      goto LABEL_4;
    }
    if ( *(struct DirectUI::Element **)a3 == v10 )
    {
      *((_QWORD *)this + 11) = qword_140080018;
      *((_DWORD *)this + 20) = 41;
      NamedElement = WizardPage::CreateAndGotoNextPage(this);
      if ( NamedElement < 0 )
      {
        v7 = 744;
        goto LABEL_4;
      }
      goto LABEL_15;
    }
  }
}

```

## disassembly

```asm
0x14003adc0  mov     [rsp-8+arg_0], rbx
0x14003adc5  push    rbp
0x14003adc6  push    rsi
0x14003adc7  push    rdi
0x14003adc8  lea     rbp, [rsp-47h]
0x14003adcd  sub     rsp, 0A0h
0x14003add4  mov     rbx, rdx
0x14003add7  mov     [rbp+57h+arg_10], 0
0x14003addf  xor     edx, edx; Val
0x14003ade1  mov     rsi, r8
0x14003ade4  mov     rdi, rcx
0x14003ade7  lea     rcx, [rbp+57h+pExecInfo]; void *
0x14003adeb  lea     r8d, [rdx+70h]; Size
0x14003adef  call    memset_0
0x14003adf4  mov     r8, rsi; struct DirectUI::Event *
0x14003adf7  mov     rdx, rbx; struct DirectUI::Element *
0x14003adfa  mov     rcx, rdi; this
0x14003adfd  call    ?OnListenedEvent@WizardPage@@UEAAXPEAVElement@DirectUI@@PEAUEvent@3@@Z; WizardPage::OnListenedEvent(DirectUI::Element *,DirectUI::Event *)
0x14003ae02  mov     rax, cs:__imp_?Click@Button@DirectUI@@SA?AVUID@@XZ; DirectUI::Button::Click(void)
0x14003ae09  lea     rcx, [rsi+8]
0x14003ae0d  lea     rdx, [rbp+57h+arg_18]
0x14003ae11  mov     [rbp+57h+arg_18], rax
0x14003ae15  call    ??8@YA_NAEBVUID@@AEBQ6A?AV0@XZ@Z; operator==(UID const &,UID (*const &)(void))
0x14003ae1a  test    al, al
0x14003ae1c  jz      loc_14003AF2D
0x14003ae22  lea     r8, [rbp+57h+arg_10]; struct DirectUI::Element **
0x14003ae26  mov     rcx, rdi; this
0x14003ae29  lea     rdx, aLinkhistory; "linkHistory"
0x14003ae30  call    ?GetNamedElement@WizardPage@@QEAAJPEBGPEAPEAVElement@DirectUI@@@Z; WizardPage::GetNamedElement(ushort const *,DirectUI::Element * *)
0x14003ae35  test    eax, eax
0x14003ae37  jns     short loc_14003AE60
0x14003ae39  mov     r9d, 2BAh
0x14003ae3f  mov     ecx, 1; Level
0x14003ae44  lea     rdx, aDwzErrorSDHr0x; "Dwz ERROR: %s:%d - hr = 0x%08X\n"
0x14003ae4b  mov     [rsp+0B0h+var_90], eax
0x14003ae4f  lea     r8, aUploadfailurep_0; "UploadFailurePage::OnListenedEvent"
0x14003ae56  call    ?SdpDebugPrint@@YAXKPEBDZZ; SdpDebugPrint(ulong,char const *,...)
0x14003ae5b  jmp     loc_14003AF2D
0x14003ae60  mov     rax, [rbp+57h+arg_10]
0x14003ae64  mov     ebx, 1
0x14003ae69  cmp     [rsi], rax
0x14003ae6c  jnz     short loc_14003AEDD
0x14003ae6e  lea     rax, Operation; "open"
0x14003ae75  mov     [rbp+57h+pExecInfo.cbSize], 70h ; 'p'
0x14003ae7c  mov     [rbp+57h+pExecInfo.lpVerb], rax
0x14003ae80  lea     rcx, [rbp+57h+pExecInfo]; pExecInfo
0x14003ae84  lea     rax, aControlExe; "control.exe"
0x14003ae8b  mov     [rbp+57h+pExecInfo.fMask], 400h
0x14003ae92  mov     [rbp+57h+pExecInfo.lpFile], rax
0x14003ae96  lea     rax, aNameMicrosoftT_0; "/name Microsoft.Troubleshooting /page h"...
0x14003ae9d  mov     [rbp+57h+pExecInfo.lpParameters], rax
0x14003aea1  mov     [rbp+57h+pExecInfo.nShow], ebx
0x14003aea4  call    cs:__imp_ShellExecuteExW
0x14003aeab  nop     dword ptr [rax+rax+00h]
0x14003aeb0  test    eax, eax
0x14003aeb2  jnz     short loc_14003AF2A
0x14003aeb4  call    cs:__imp_GetLastError
0x14003aebb  nop     dword ptr [rax+rax+00h]
0x14003aec0  test    eax, eax
0x14003aec2  jle     short loc_14003AECE
0x14003aec4  movzx   eax, ax
0x14003aec7  or      eax, 80070000h
0x14003aecc  test    eax, eax
0x14003aece  jns     short loc_14003AF2A
0x14003aed0  mov     r9d, 2C8h
0x14003aed6  mov     ecx, ebx
0x14003aed8  jmp     loc_14003AE44
0x14003aedd  lea     r8, [rbp+57h+arg_10]; struct DirectUI::Element **
0x14003aee1  mov     rcx, rdi; this
0x14003aee4  lea     rdx, aLinkignore; "linkIgnore"
0x14003aeeb  call    ?GetNamedElement@WizardPage@@QEAAJPEBGPEAPEAVElement@DirectUI@@@Z; WizardPage::GetNamedElement(ushort const *,DirectUI::Element * *)
0x14003aef0  test    eax, eax
0x14003aef2  jns     short loc_14003AEFC
0x14003aef4  mov     r9d, 2D2h
0x14003aefa  jmp     short loc_14003AED6
0x14003aefc  mov     rax, [rbp+57h+arg_10]
0x14003af00  mov     rcx, rdi; this
0x14003af03  cmp     [rsi], rax
0x14003af06  jnz     short loc_14003AF41
0x14003af08  mov     rax, cs:?Config@@3PEAVConfiguration@@EA; Configuration * Config
0x14003af0f  xor     r9d, r9d
0x14003af12  mov     edx, 471h
0x14003af17  lea     r8d, [r9+5]
0x14003af1b  mov     [rax+0Ch], ebx
0x14003af1e  call    cs:__imp_?PropSheet_SendMessage@TaskPage@DirectUI@@IEAA_JI_K_J@Z; DirectUI::TaskPage::PropSheet_SendMessage(uint,unsigned __int64,__int64)
0x14003af25  nop     dword ptr [rax+rax+00h]
0x14003af2a  mov     [rsi+10h], bl
0x14003af2d  mov     rbx, [rsp+0B0h+arg_0]
0x14003af35  add     rsp, 0A0h
0x14003af3c  pop     rdi
0x14003af3d  pop     rsi
0x14003af3e  pop     rbp
0x14003af3f  retn
0x14003af41  lea     r8, [rbp+57h+arg_10]; struct DirectUI::Element **
0x14003af45  lea     rdx, aLinkretry; "linkRetry"
0x14003af4c  call    ?GetNamedElement@WizardPage@@QEAAJPEBGPEAPEAVElement@DirectUI@@@Z; WizardPage::GetNamedElement(ushort const *,DirectUI::Element * *)
0x14003af51  test    eax, eax
0x14003af53  jns     short loc_14003AF60
0x14003af55  mov     r9d, 2E1h
0x14003af5b  jmp     loc_14003AED6
0x14003af60  mov     rax, [rbp+57h+arg_10]
0x14003af64  cmp     [rsi], rax
0x14003af67  jnz     short loc_14003AF2D
0x14003af69  mov     rax, cs:qword_140080018
0x14003af70  mov     rcx, rdi; this
0x14003af73  mov     [rdi+58h], rax
0x14003af77  mov     dword ptr [rdi+50h], 29h ; ')'
0x14003af7e  call    ?CreateAndGotoNextPage@WizardPage@@IEAAJXZ; WizardPage::CreateAndGotoNextPage(void)
0x14003af83  test    eax, eax
0x14003af85  jns     short loc_14003AF2A
0x14003af87  mov     r9d, 2E8h
0x14003af8d  jmp     loc_14003AED6
```
