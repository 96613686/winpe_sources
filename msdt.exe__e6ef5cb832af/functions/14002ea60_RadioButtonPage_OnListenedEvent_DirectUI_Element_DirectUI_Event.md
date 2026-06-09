# RadioButtonPage::OnListenedEvent(DirectUI::Element *,DirectUI::Event *)

- ea: `0x14002ea60`
- end: `0x14002ec4f`
- name: `?OnListenedEvent@RadioButtonPage@@MEAAXPEAVElement@DirectUI@@PEAUEvent@3@@Z`
- size: `495`
- prototype: `void __fastcall(RadioButtonPage *__hidden this, struct DirectUI::Element *, struct DirectUI::Event *)`
- caller_count: `0`
- callee_count: `9`
- tags: `service_task`

## callees

- `0x1400070b0`
- `0x14000dd7c`
- `0x14000e6bc`
- `0x14000e72c`
- `0x14000f0e0`
- `0x140020420`
- `0x14002e820`
- `0x14002ea60`
- `0x140061c90`

## import_xrefs

- `USER32!PostMessageW` at `0x14002eb33`
- `USER32!PostMessageW` at `0x14002ebf5`
- `USER32!PostMessageW` at `0x14002eb33`
- `USER32!PostMessageW` at `0x14002ebf5`
- `DUI70!?PropSheet_SendMessage@TaskPage@DirectUI@@IEAA_JI_K_J@Z` at `0x14002eb84`
- `DUI70!?PropSheet_SendMessage@TaskPage@DirectUI@@IEAA_JI_K_J@Z` at `0x14002eb84`
- `DUI70!?Click@Button@DirectUI@@SA?AVUID@@XZ` at `0x14002ea9f`

## pseudocode

```c
void __fastcall RadioButtonPage::OnListenedEvent(HWND *this, struct DirectUI::Element *a2, struct DirectUI::Event *a3)
{
  int v6; // esi
  unsigned int v7; // r14d
  int NamedElement; // eax
  int v9; // eax
  unsigned int v10; // eax
  unsigned int v11; // edi
  int v12; // r9d
  struct DirectUI::Element *v13; // [rsp+30h] [rbp-40h] BYREF
  HWND hWnd; // [rsp+38h] [rbp-38h] BYREF
  __int64 v15; // [rsp+40h] [rbp-30h] BYREF
  unsigned __int16 v16[12]; // [rsp+48h] [rbp-28h] BYREF

  v13 = 0;
  hWnd = 0;
  WizardPage::OnListenedEvent((WizardPage *)this, a2, a3);
  v15 = DirectUI::Button::Click;
  if ( !(unsigned __int8)operator==((char *)a3 + 8, &v15) )
    goto LABEL_7;
  v6 = 0;
  if ( !*((_DWORD *)this + 42) )
    goto LABEL_7;
  while ( 1 )
  {
    v7 = v6 + 1;
    NamedElement = StringCchPrintfW(v16, 0xAu, L"rb%d", (unsigned int)(v6 + 1));
    if ( NamedElement < 0 )
    {
      v12 = 2224;
      goto LABEL_24;
    }
    NamedElement = WizardPage::GetNamedElement((WizardPage *)this, v16, &v13);
    if ( NamedElement < 0 )
    {
      v12 = 2227;
LABEL_24:
      SdpDebugPrint(1u, "Dwz ERROR: %s:%d - hr = 0x%08X\n", "RadioButtonPage::OnListenedEvent", v12, NamedElement);
      return;
    }
    if ( *(struct DirectUI::Element **)a3 == v13 )
      break;
    ++v6;
    if ( v7 >= *((_DWORD *)this + 42) )
      goto LABEL_7;
  }
  if ( *((_DWORD *)this + 46) )
  {
    v9 = 0;
    *((_DWORD *)this + 46) = 0;
  }
  else
  {
    DirectUI::TaskPage::PropSheet_SendMessage((DirectUI::TaskPage *)this, 0x48Bu, 2u, 2);
    v9 = 1;
  }
  *((_BYTE *)a3 + 16) = 1;
  if ( v9 )
  {
    v10 = 0;
    if ( *((_DWORD *)this + 42) )
    {
      while ( 1 )
      {
        v11 = v10 + 1;
        if ( v6 != v10 )
        {
          NamedElement = StringCchPrintfW(v16, 0xAu, L"rb%d", v11);
          if ( NamedElement < 0 )
          {
            v12 = 2264;
            goto LABEL_24;
          }
          NamedElement = WizardPage::GetNamedHandle((WizardPage *)this, v16, &hWnd);
          if ( NamedElement < 0 )
          {
            v12 = 2267;
            goto LABEL_24;
          }
          PostMessageW(hWnd, 0xF1u, 0, 0);
        }
        v10 = v11;
        if ( v11 >= *((_DWORD *)this + 42) )
          goto LABEL_8;
      }
    }
    goto LABEL_8;
  }
LABEL_7:
  InteractivityPage::OnListenedEvent((InteractivityPage *)this, a2, a3);
LABEL_8:
  PostMessageW(this[7], 0x9E7u, 0, 0);
}

```

## disassembly

```asm
0x14002ea60  mov     [rsp-28h+arg_8], rbx
0x14002ea65  push    rbp
0x14002ea66  push    rsi
0x14002ea67  push    rdi
0x14002ea68  push    r14
0x14002ea6a  push    r15
0x14002ea6c  mov     rbp, rsp
0x14002ea6f  sub     rsp, 70h
0x14002ea73  mov     rax, cs:__security_cookie
0x14002ea7a  xor     rax, rsp
0x14002ea7d  mov     [rbp+var_10], rax
0x14002ea81  mov     rdi, r8
0x14002ea84  mov     [rbp+var_40], 0
0x14002ea8c  mov     r15, rdx
0x14002ea8f  mov     [rbp+hWnd], 0
0x14002ea97  mov     rbx, rcx
0x14002ea9a  call    ?OnListenedEvent@WizardPage@@UEAAXPEAVElement@DirectUI@@PEAUEvent@3@@Z; WizardPage::OnListenedEvent(DirectUI::Element *,DirectUI::Event *)
0x14002ea9f  mov     rax, cs:__imp_?Click@Button@DirectUI@@SA?AVUID@@XZ; DirectUI::Button::Click(void)
0x14002eaa6  lea     rcx, [rdi+8]
0x14002eaaa  lea     rdx, [rbp+var_30]
0x14002eaae  mov     [rbp+var_30], rax
0x14002eab2  call    ??8@YA_NAEBVUID@@AEBQ6A?AV0@XZ@Z; operator==(UID const &,UID (*const &)(void))
0x14002eab7  test    al, al
0x14002eab9  jz      short loc_14002EB16
0x14002eabb  xor     esi, esi
0x14002eabd  cmp     [rbx+0A8h], esi
0x14002eac3  jbe     short loc_14002EB16
0x14002eac5  lea     r14d, [rsi+1]
0x14002eac9  mov     edx, 0Ah; unsigned __int64
0x14002eace  mov     r9d, r14d
0x14002ead1  lea     r8, aRbD; "rb%d"
0x14002ead8  lea     rcx, [rbp+var_28]; unsigned __int16 *
0x14002eadc  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x14002eae1  test    eax, eax
0x14002eae3  js      loc_14002EC28
0x14002eae9  lea     r8, [rbp+var_40]; struct DirectUI::Element **
0x14002eaed  mov     rcx, rbx; this
0x14002eaf0  lea     rdx, [rbp+var_28]; unsigned __int16 *
0x14002eaf4  call    ?GetNamedElement@WizardPage@@QEAAJPEBGPEAPEAVElement@DirectUI@@@Z; WizardPage::GetNamedElement(ushort const *,DirectUI::Element * *)
0x14002eaf9  test    eax, eax
0x14002eafb  js      loc_14002EC20
0x14002eb01  mov     rax, [rbp+var_40]
0x14002eb05  cmp     [rdi], rax
0x14002eb08  jz      short loc_14002EB60
0x14002eb0a  mov     esi, r14d
0x14002eb0d  cmp     r14d, [rbx+0A8h]
0x14002eb14  jb      short loc_14002EAC5
0x14002eb16  mov     r8, rdi; struct DirectUI::Event *
0x14002eb19  mov     rdx, r15; struct DirectUI::Element *
0x14002eb1c  mov     rcx, rbx; this
0x14002eb1f  call    ?OnListenedEvent@InteractivityPage@@UEAAXPEAVElement@DirectUI@@PEAUEvent@3@@Z; InteractivityPage::OnListenedEvent(DirectUI::Element *,DirectUI::Event *)
0x14002eb24  mov     rcx, [rbx+38h]; hWnd
0x14002eb28  xor     r9d, r9d; lParam
0x14002eb2b  xor     r8d, r8d; wParam
0x14002eb2e  mov     edx, 9E7h; Msg
0x14002eb33  call    cs:__imp_PostMessageW
0x14002eb3a  nop     dword ptr [rax+rax+00h]
0x14002eb3f  mov     rcx, [rbp+var_10]
0x14002eb43  xor     rcx, rsp; StackCookie
0x14002eb46  call    __security_check_cookie
0x14002eb4b  mov     rbx, [rsp+70h+arg_8]
0x14002eb53  add     rsp, 70h
0x14002eb57  pop     r15
0x14002eb59  pop     r14
0x14002eb5b  pop     rdi
0x14002eb5c  pop     rsi
0x14002eb5d  pop     rbp
0x14002eb5e  retn
0x14002eb60  cmp     dword ptr [rbx+0B8h], 0
0x14002eb67  jz      short loc_14002EB73
0x14002eb69  xor     eax, eax
0x14002eb6b  mov     [rbx+0B8h], eax
0x14002eb71  jmp     short loc_14002EB95
0x14002eb73  mov     r8d, 2
0x14002eb79  mov     edx, 48Bh
0x14002eb7e  mov     r9d, r8d
0x14002eb81  mov     rcx, rbx
0x14002eb84  call    cs:__imp_?PropSheet_SendMessage@TaskPage@DirectUI@@IEAA_JI_K_J@Z; DirectUI::TaskPage::PropSheet_SendMessage(uint,unsigned __int64,__int64)
0x14002eb8b  nop     dword ptr [rax+rax+00h]
0x14002eb90  mov     eax, 1
0x14002eb95  mov     byte ptr [rdi+10h], 1
0x14002eb99  test    eax, eax
0x14002eb9b  jz      loc_14002EB16
0x14002eba1  xor     eax, eax
0x14002eba3  cmp     [rbx+0A8h], eax
0x14002eba9  jbe     loc_14002EB24
0x14002ebaf  lea     edi, [rax+1]
0x14002ebb2  cmp     esi, eax
0x14002ebb4  jz      short loc_14002EC01
0x14002ebb6  mov     r9d, edi
0x14002ebb9  lea     r8, aRbD; "rb%d"
0x14002ebc0  mov     edx, 0Ah; unsigned __int64
0x14002ebc5  lea     rcx, [rbp+var_28]; unsigned __int16 *
0x14002ebc9  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x14002ebce  test    eax, eax
0x14002ebd0  js      short loc_14002EC18
0x14002ebd2  lea     r8, [rbp+hWnd]; HWND *
0x14002ebd6  mov     rcx, rbx; this
0x14002ebd9  lea     rdx, [rbp+var_28]; unsigned __int16 *
0x14002ebdd  call    ?GetNamedHandle@WizardPage@@IEAAJPEBGPEAPEAUHWND__@@@Z; WizardPage::GetNamedHandle(ushort const *,HWND__ * *)
0x14002ebe2  test    eax, eax
0x14002ebe4  js      short loc_14002EC10
0x14002ebe6  mov     rcx, [rbp+hWnd]; hWnd
0x14002ebea  xor     r9d, r9d; lParam
0x14002ebed  xor     r8d, r8d; wParam
0x14002ebf0  mov     edx, 0F1h; Msg
0x14002ebf5  call    cs:__imp_PostMessageW
0x14002ebfc  nop     dword ptr [rax+rax+00h]
0x14002ec01  mov     eax, edi
0x14002ec03  cmp     eax, [rbx+0A8h]
0x14002ec09  jb      short loc_14002EBAF
0x14002ec0b  jmp     loc_14002EB24
0x14002ec10  mov     r9d, 8DBh
0x14002ec16  jmp     short loc_14002EC2E
0x14002ec18  mov     r9d, 8D8h
0x14002ec1e  jmp     short loc_14002EC2E
0x14002ec20  mov     r9d, 8B3h
0x14002ec26  jmp     short loc_14002EC2E
0x14002ec28  mov     r9d, 8B0h
0x14002ec2e  lea     r8, aRadiobuttonpag_2; "RadioButtonPage::OnListenedEvent"
0x14002ec35  mov     [rsp+70h+var_50], eax
0x14002ec39  lea     rdx, aDwzErrorSDHr0x; "Dwz ERROR: %s:%d - hr = 0x%08X\n"
0x14002ec40  mov     ecx, 1; Level
0x14002ec45  call    ?SdpDebugPrint@@YAXKPEBDZZ; SdpDebugPrint(ulong,char const *,...)
0x14002ec4a  jmp     loc_14002EB3F
```
