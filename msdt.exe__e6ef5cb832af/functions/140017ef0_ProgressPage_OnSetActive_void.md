# ProgressPage::OnSetActive(void)

- ea: `0x140017ef0`
- end: `0x1400181fe`
- name: `?OnSetActive@ProgressPage@@MEAA_JXZ`
- size: `782`
- prototype: `__int64 __fastcall(void **this)`
- caller_count: `0`
- callee_count: `6`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x14000e6bc`
- `0x14000f480`
- `0x140010680`
- `0x140017ef0`
- `0x1400186b4`
- `0x140020420`

## import_xrefs

- `KERNEL32!GetLastError` at `0x14001803c`
- `KERNEL32!GetLastError` at `0x1400180b9`
- `KERNEL32!GetLastError` at `0x140018160`
- `KERNEL32!GetLastError` at `0x14001819c`
- `KERNEL32!GetLastError` at `0x14001803c`
- `KERNEL32!GetLastError` at `0x1400180b9`
- `KERNEL32!GetLastError` at `0x140018160`
- `KERNEL32!GetLastError` at `0x14001819c`
- `KERNEL32!DeleteTimerQueueTimer` at `0x140018027`
- `KERNEL32!DeleteTimerQueueTimer` at `0x1400180ec`
- `KERNEL32!DeleteTimerQueueTimer` at `0x140018027`
- `KERNEL32!DeleteTimerQueueTimer` at `0x1400180ec`
- `KERNEL32!CreateTimerQueueTimer` at `0x1400180a9`
- `KERNEL32!CreateTimerQueueTimer` at `0x1400180a9`
- `KERNEL32!SetEvent` at `0x140018150`
- `KERNEL32!SetEvent` at `0x14001818c`
- `KERNEL32!SetEvent` at `0x140018150`
- `KERNEL32!SetEvent` at `0x14001818c`
- `USER32!PostMessageW` at `0x140018132`
- `USER32!PostMessageW` at `0x140018132`
- `ole32!CoCreateInstance` at `0x140017f62`
- `ole32!CoCreateInstance` at `0x140017f62`
- `DUI70!?SetVisible@Element@DirectUI@@QEAAJ_N@Z` at `0x140017fd1`
- `DUI70!?SetVisible@Element@DirectUI@@QEAAJ_N@Z` at `0x140017fd1`
- `DUI70!?EndDefer@Element@DirectUI@@QEAAXK@Z` at `0x1400181e1`
- `DUI70!?EndDefer@Element@DirectUI@@QEAAXK@Z` at `0x1400181e1`
- `DUI70!?GetElement@TaskPage@DirectUI@@IEAAPEAVElement@2@XZ` at `0x140017f08`
- `DUI70!?GetElement@TaskPage@DirectUI@@IEAAPEAVElement@2@XZ` at `0x140017f08`
- `DUI70!?StartDefer@Element@DirectUI@@QEAAXPEAK@Z` at `0x140017f25`
- `DUI70!?StartDefer@Element@DirectUI@@QEAAXPEAK@Z` at `0x140017f25`
- `DUI70!?GetParentHWND@TaskPage@DirectUI@@QEAAPEAUHWND__@@XZ` at `0x14001807e`
- `DUI70!?GetParentHWND@TaskPage@DirectUI@@QEAAPEAUHWND__@@XZ` at `0x140018118`
- `DUI70!?GetParentHWND@TaskPage@DirectUI@@QEAAPEAUHWND__@@XZ` at `0x14001807e`
- `DUI70!?GetParentHWND@TaskPage@DirectUI@@QEAAPEAUHWND__@@XZ` at `0x140018118`

## pseudocode

```c
__int64 __fastcall ProgressPage::OnSetActive(void **this)
{
  signed int NamedElement; // eax
  int v3; // r9d
  _QWORD *v4; // rsi
  void *v5; // rdx
  signed int LastError; // eax
  HWND v7; // rax
  bool v8; // sf
  void *v9; // rdx
  HWND ParentHWND; // rax
  void *v11; // rcx
  bool v12; // sf
  bool v13; // sf
  LPVOID *ppv; // [rsp+20h] [rbp-68h]
  DirectUI::Element *Element; // [rsp+40h] [rbp-48h]
  unsigned int v17[16]; // [rsp+48h] [rbp-40h] BYREF
  struct DirectUI::Element *v18; // [rsp+90h] [rbp+8h] BYREF

  v18 = 0;
  Element = DirectUI::TaskPage::GetElement((DirectUI::TaskPage *)this);
  v17[0] = 0;
  DirectUI::Element::StartDefer(Element, v17);
  WizardPage::OnSetActive((WizardPage *)this);
  if ( !this[19] )
    CoCreateInstance(&CLSID_TaskbarList, 0, 1u, &GUID_ea1afb91_9e28_4b86_90e9_9e9f8a5eefaf, this + 19);
  NamedElement = WizardPage::GetNamedElement((WizardPage *)this, L"page", &v18);
  if ( NamedElement < 0 )
  {
    v3 = 1188;
LABEL_5:
    SdpDebugPrint(1u, "Dwz ERROR: %s:%d - hr = 0x%08X\n", "ProgressPage::OnSetActive", v3, NamedElement);
    goto LABEL_40;
  }
  if ( *((_DWORD *)this + 33) )
  {
    NamedElement = ProgressPage::SetVisible((ProgressPage *)this);
    if ( NamedElement < 0 )
    {
      v3 = 1231;
      goto LABEL_5;
    }
    ParentHWND = DirectUI::TaskPage::GetParentHWND((DirectUI::TaskPage *)this);
    PostMessageW(ParentHWND, 0x9E6u, 0, 0);
  }
  else
  {
    NamedElement = DirectUI::Element::SetVisible(v18, 0);
    if ( NamedElement < 0 )
    {
      v3 = 1192;
      goto LABEL_5;
    }
    NamedElement = WizardPage::SetNamedValues(
                     (WizardPage *)this,
                     L"txtSubProgress",
                     L" ",
                     0,
                     (const unsigned __int16 *)ppv,
                     0);
    if ( NamedElement < 0 )
    {
      v3 = 1195;
      goto LABEL_5;
    }
    v4 = this + 14;
    v5 = this[14];
    if ( v5 )
    {
      if ( DeleteTimerQueueTimer(0, v5, 0) )
      {
        *v4 = 0;
      }
      else
      {
        LastError = GetLastError();
        if ( LastError > 0 )
          LastError = (unsigned __int16)LastError | 0x80070000;
        *v4 = 0;
        if ( LastError < 0 )
          SdpDebugPrint(1u, "Dwz IGNORED: %s:%d - hr = 0x%08X\n", "ProgressPage::OnSetActive", 1203, LastError);
      }
    }
    *((_DWORD *)this + 32) = 0;
    v7 = DirectUI::TaskPage::GetParentHWND((DirectUI::TaskPage *)this);
    if ( !CreateTimerQueueTimer(this + 14, 0, ProgressPage::ShowContentsAfterTimeoutCallback, v7, 0x1F4u, 0, 0) )
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
        v3 = 1215;
        goto LABEL_5;
      }
    }
    v9 = this[15];
    if ( v9 )
    {
      DeleteTimerQueueTimer(0, v9, 0);
      this[15] = 0;
    }
  }
  *((_DWORD *)this + 33) = 0;
  v11 = this[17];
  if ( v11 && !SetEvent(v11) )
  {
    NamedElement = GetLastError();
    v12 = NamedElement < 0;
    if ( NamedElement > 0 )
    {
      NamedElement = (unsigned __int16)NamedElement | 0x80070000;
      v12 = NamedElement < 0;
    }
    if ( v12 )
    {
      v3 = 1240;
      goto LABEL_5;
    }
  }
  if ( !SetEvent(g_ProgressPageLoaded) )
  {
    NamedElement = GetLastError();
    v13 = NamedElement < 0;
    if ( NamedElement > 0 )
    {
      NamedElement = (unsigned __int16)NamedElement | 0x80070000;
      v13 = NamedElement < 0;
    }
    if ( v13 )
    {
      v3 = 1244;
      goto LABEL_5;
    }
  }
  *((_DWORD *)this + 20) = ProgressPage::s_NextType;
  ProgressPage::s_NextType = 55;
LABEL_40:
  if ( v17[0] )
    DirectUI::Element::EndDefer(Element, v17[0]);
  return 0;
}

```

## disassembly

```asm
0x140017ef0  mov     rax, rsp
0x140017ef3  push    rbx
0x140017ef4  push    rbp
0x140017ef5  push    rsi
0x140017ef6  push    rdi
0x140017ef7  push    r14
0x140017ef9  push    r15
0x140017efb  sub     rsp, 58h
0x140017eff  mov     rbx, rcx
0x140017f02  xor     ebp, ebp
0x140017f04  mov     [rax+8], rbp
0x140017f08  call    cs:__imp_?GetElement@TaskPage@DirectUI@@IEAAPEAVElement@2@XZ; DirectUI::TaskPage::GetElement(void)
0x140017f0f  nop     dword ptr [rax+rax+00h]
0x140017f14  mov     [rsp+88h+var_48], rax
0x140017f19  mov     [rsp+88h+var_40], ebp
0x140017f1d  lea     rdx, [rsp+88h+var_40]
0x140017f22  mov     rcx, rax
0x140017f25  call    cs:__imp_?StartDefer@Element@DirectUI@@QEAAXPEAK@Z; DirectUI::Element::StartDefer(ulong *)
0x140017f2c  nop     dword ptr [rax+rax+00h]
0x140017f31  nop
0x140017f32  mov     rcx, rbx; this
0x140017f35  call    ?OnSetActive@WizardPage@@MEAA_JXZ; WizardPage::OnSetActive(void)
0x140017f3a  lea     rax, [rbx+98h]
0x140017f41  lea     r14d, [rbp+1]
0x140017f45  cmp     [rax], rbp
0x140017f48  jnz     short loc_140017F6E
0x140017f4a  mov     [rsp+88h+ppv], rax; unsigned __int16 *
0x140017f4f  lea     r9, _GUID_ea1afb91_9e28_4b86_90e9_9e9f8a5eefaf; riid
0x140017f56  mov     r8d, r14d; dwClsContext
0x140017f59  xor     edx, edx; pUnkOuter
0x140017f5b  lea     rcx, CLSID_TaskbarList; rclsid
0x140017f62  call    cs:__imp_CoCreateInstance
0x140017f69  nop     dword ptr [rax+rax+00h]
0x140017f6e  lea     r8, [rsp+88h+arg_0]; struct DirectUI::Element **
0x140017f76  lea     rdx, aPage; "page"
0x140017f7d  mov     rcx, rbx; this
0x140017f80  call    ?GetNamedElement@WizardPage@@QEAAJPEBGPEAPEAVElement@DirectUI@@@Z; WizardPage::GetNamedElement(ushort const *,DirectUI::Element * *)
0x140017f85  test    eax, eax
0x140017f87  jns     short loc_140017FAE
0x140017f89  mov     r9d, 4A4h
0x140017f8f  lea     r8, aProgresspageOn_1; "ProgressPage::OnSetActive"
0x140017f96  mov     dword ptr [rsp+88h+ppv], eax
0x140017f9a  lea     rdx, aDwzErrorSDHr0x; "Dwz ERROR: %s:%d - hr = 0x%08X\n"
0x140017fa1  mov     ecx, r14d; Level
0x140017fa4  call    ?SdpDebugPrint@@YAXKPEBDZZ; SdpDebugPrint(ulong,char const *,...)
0x140017fa9  jmp     loc_1400181D4
0x140017fae  lea     rdi, aProgresspageOn_1; "ProgressPage::OnSetActive"
0x140017fb5  mov     r15d, 80070000h
0x140017fbb  cmp     [rbx+84h], ebp
0x140017fc1  jnz     loc_1400180FE
0x140017fc7  xor     edx, edx
0x140017fc9  mov     rcx, [rsp+88h+arg_0]
0x140017fd1  call    cs:__imp_?SetVisible@Element@DirectUI@@QEAAJ_N@Z; DirectUI::Element::SetVisible(bool)
0x140017fd8  nop     dword ptr [rax+rax+00h]
0x140017fdd  test    eax, eax
0x140017fdf  jns     short loc_140017FEC
0x140017fe1  mov     r9d, 4A8h
0x140017fe7  mov     r8, rdi
0x140017fea  jmp     short loc_140017F96
0x140017fec  mov     qword ptr [rsp+88h+Period], rbp; unsigned __int16 *
0x140017ff1  xor     r9d, r9d; unsigned __int16 *
0x140017ff4  lea     r8, pszSubIdList; " "
0x140017ffb  lea     rdx, aTxtsubprogress; "txtSubProgress"
0x140018002  mov     rcx, rbx; this
0x140018005  call    ?SetNamedValues@WizardPage@@IEAAJPEBG0000@Z; WizardPage::SetNamedValues(ushort const *,ushort const *,ushort const *,ushort const *,ushort const *)
0x14001800a  test    eax, eax
0x14001800c  jns     short loc_140018016
0x14001800e  mov     r9d, 4ABh
0x140018014  jmp     short loc_140017FE7
0x140018016  lea     rsi, [rbx+70h]
0x14001801a  mov     rdx, [rsi]; Timer
0x14001801d  test    rdx, rdx
0x140018020  jz      short loc_140018075
0x140018022  xor     r8d, r8d; CompletionEvent
0x140018025  xor     ecx, ecx; TimerQueue
0x140018027  call    cs:__imp_DeleteTimerQueueTimer
0x14001802e  nop     dword ptr [rax+rax+00h]
0x140018033  test    eax, eax
0x140018035  jz      short loc_14001803C
0x140018037  mov     [rsi], rbp
0x14001803a  jmp     short loc_140018075
0x14001803c  call    cs:__imp_GetLastError
0x140018043  nop     dword ptr [rax+rax+00h]
0x140018048  test    eax, eax
0x14001804a  jle     short loc_140018052
0x14001804c  movzx   eax, ax
0x14001804f  or      eax, r15d
0x140018052  mov     [rsi], rbp
0x140018055  test    eax, eax
0x140018057  jns     short loc_140018075
0x140018059  mov     dword ptr [rsp+88h+ppv], eax
0x14001805d  mov     r9d, 4B3h
0x140018063  mov     r8, rdi
0x140018066  lea     rdx, aDwzIgnoredSDHr; "Dwz IGNORED: %s:%d - hr = 0x%08X\n"
0x14001806d  mov     ecx, r14d; Level
0x140018070  call    ?SdpDebugPrint@@YAXKPEBDZZ; SdpDebugPrint(ulong,char const *,...)
0x140018075  mov     [rbx+80h], ebp
0x14001807b  mov     rcx, rbx
0x14001807e  call    cs:__imp_?GetParentHWND@TaskPage@DirectUI@@QEAAPEAUHWND__@@XZ; DirectUI::TaskPage::GetParentHWND(void)
0x140018085  nop     dword ptr [rax+rax+00h]
0x14001808a  mov     r9, rax; Parameter
0x14001808d  mov     [rsp+88h+Flags], ebp; Flags
0x140018091  mov     [rsp+88h+Period], ebp; Period
0x140018095  mov     dword ptr [rsp+88h+ppv], 1F4h; DueTime
0x14001809d  lea     r8, ?ShowContentsAfterTimeoutCallback@ProgressPage@@KAXPEAXE@Z; Callback
0x1400180a4  xor     edx, edx; TimerQueue
0x1400180a6  mov     rcx, rsi; phNewTimer
0x1400180a9  call    cs:__imp_CreateTimerQueueTimer
0x1400180b0  nop     dword ptr [rax+rax+00h]
0x1400180b5  test    eax, eax
0x1400180b7  jnz     short loc_1400180DE
0x1400180b9  call    cs:__imp_GetLastError
0x1400180c0  nop     dword ptr [rax+rax+00h]
0x1400180c5  test    eax, eax
0x1400180c7  jle     short loc_1400180D1
0x1400180c9  movzx   eax, ax
0x1400180cc  or      eax, r15d
0x1400180cf  test    eax, eax
0x1400180d1  jns     short loc_1400180DE
0x1400180d3  mov     r9d, 4BFh
0x1400180d9  jmp     loc_140017FE7
0x1400180de  mov     rdx, [rbx+78h]; Timer
0x1400180e2  test    rdx, rdx
0x1400180e5  jz      short loc_14001813E
0x1400180e7  xor     r8d, r8d; CompletionEvent
0x1400180ea  xor     ecx, ecx; TimerQueue
0x1400180ec  call    cs:__imp_DeleteTimerQueueTimer
0x1400180f3  nop     dword ptr [rax+rax+00h]
0x1400180f8  mov     [rbx+78h], rbp
0x1400180fc  jmp     short loc_14001813E
0x1400180fe  mov     rcx, rbx; this
0x140018101  call    ?SetVisible@ProgressPage@@QEAAJXZ; ProgressPage::SetVisible(void)
0x140018106  test    eax, eax
0x140018108  jns     short loc_140018115
0x14001810a  mov     r9d, 4CFh
0x140018110  jmp     loc_140017FE7
0x140018115  mov     rcx, rbx
0x140018118  call    cs:__imp_?GetParentHWND@TaskPage@DirectUI@@QEAAPEAUHWND__@@XZ; DirectUI::TaskPage::GetParentHWND(void)
0x14001811f  nop     dword ptr [rax+rax+00h]
0x140018124  mov     rcx, rax; hWnd
0x140018127  xor     r9d, r9d; lParam
0x14001812a  xor     r8d, r8d; wParam
0x14001812d  mov     edx, 9E6h; Msg
0x140018132  call    cs:__imp_PostMessageW
0x140018139  nop     dword ptr [rax+rax+00h]
0x14001813e  mov     [rbx+84h], ebp
0x140018144  mov     rcx, [rbx+88h]; hEvent
0x14001814b  test    rcx, rcx
0x14001814e  jz      short loc_140018185
0x140018150  call    cs:__imp_SetEvent
0x140018157  nop     dword ptr [rax+rax+00h]
0x14001815c  test    eax, eax
0x14001815e  jnz     short loc_140018185
0x140018160  call    cs:__imp_GetLastError
0x140018167  nop     dword ptr [rax+rax+00h]
0x14001816c  test    eax, eax
0x14001816e  jle     short loc_140018178
0x140018170  movzx   eax, ax
0x140018173  or      eax, r15d
0x140018176  test    eax, eax
0x140018178  jns     short loc_140018185
0x14001817a  mov     r9d, 4D8h
0x140018180  jmp     loc_140017FE7
0x140018185  mov     rcx, cs:?g_ProgressPageLoaded@@3PEAXEA; hEvent
0x14001818c  call    cs:__imp_SetEvent
0x140018193  nop     dword ptr [rax+rax+00h]
0x140018198  test    eax, eax
0x14001819a  jnz     short loc_1400181C1
0x14001819c  call    cs:__imp_GetLastError
0x1400181a3  nop     dword ptr [rax+rax+00h]
0x1400181a8  test    eax, eax
0x1400181aa  jle     short loc_1400181B4
0x1400181ac  movzx   eax, ax
0x1400181af  or      eax, r15d
0x1400181b2  test    eax, eax
0x1400181b4  jns     short loc_1400181C1
0x1400181b6  mov     r9d, 4DCh
0x1400181bc  jmp     loc_140017FE7
0x1400181c1  mov     eax, cs:?s_NextType@ProgressPage@@2W4_PAGETYPE@@A; _PAGETYPE ProgressPage::s_NextType
0x1400181c7  mov     [rbx+50h], eax
0x1400181ca  mov     cs:?s_NextType@ProgressPage@@2W4_PAGETYPE@@A, 37h ; '7'; _PAGETYPE ProgressPage::s_NextType
0x1400181d4  mov     edx, [rsp+88h+var_40]
0x1400181d8  test    edx, edx
0x1400181da  jz      short loc_1400181EE
0x1400181dc  mov     rcx, [rsp+88h+var_48]
0x1400181e1  call    cs:__imp_?EndDefer@Element@DirectUI@@QEAAXK@Z; DirectUI::Element::EndDefer(ulong)
0x1400181e8  nop     dword ptr [rax+rax+00h]
0x1400181ed  nop
0x1400181ee  xor     eax, eax
0x1400181f0  add     rsp, 58h
0x1400181f4  pop     r15
0x1400181f6  pop     r14
0x1400181f8  pop     rdi
0x1400181f9  pop     rsi
0x1400181fa  pop     rbp
0x1400181fb  pop     rbx
0x1400181fc  retn
```
