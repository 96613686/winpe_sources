# UploadFilePage::NotifyHandler(uint,unsigned __int64,__int64,__int64 *,void *)

- ea: `0x14003a760`
- end: `0x14003a9c6`
- name: `?NotifyHandler@UploadFilePage@@CAHI_K_JPEA_JPEAX@Z`
- size: `614`
- prototype: `__int64 __fastcall(int, __int64, unsigned __int64, __int64 *, WizardPage *)`
- caller_count: `0`
- callee_count: `6`
- tags: `file_ops, loader_planting, service_task`

## callees

- `0x14000e6bc`
- `0x140020420`
- `0x14003a388`
- `0x14003a610`
- `0x14003a760`
- `0x140061c90`

## import_xrefs

- `USER32!GetKeyState` at `0x14003a976`
- `USER32!GetKeyState` at `0x14003a976`
- `USER32!SendMessageW` at `0x14003a876`
- `USER32!SendMessageW` at `0x14003a89d`
- `USER32!SendMessageW` at `0x14003a8f7`
- `USER32!SendMessageW` at `0x14003a876`
- `USER32!SendMessageW` at `0x14003a89d`
- `USER32!SendMessageW` at `0x14003a8f7`
- `SHELL32!ShellExecuteW` at `0x14003a843`
- `SHELL32!ShellExecuteW` at `0x14003a843`
- `DUI70!?SetEnabled@Element@DirectUI@@QEAAJ_N@Z` at `0x14003a936`
- `DUI70!?SetEnabled@Element@DirectUI@@QEAAJ_N@Z` at `0x14003a936`
- `DUI70!?PropSheet_SendMessage@TaskPage@DirectUI@@IEAA_JI_K_J@Z` at `0x14003a8dd`
- `DUI70!?PropSheet_SendMessage@TaskPage@DirectUI@@IEAA_JI_K_J@Z` at `0x14003a8dd`

## pseudocode

```c
__int64 __fastcall UploadFilePage::NotifyHandler(int a1, __int64 a2, unsigned __int64 a3, __int64 *a4, WizardPage *a5)
{
  unsigned int v5; // edi
  int v6; // eax
  HWND v7; // rsi
  int SelectedFile; // eax
  unsigned int v9; // r15d
  unsigned int i; // ebp
  int v11; // eax
  unsigned int v12; // ecx
  bool v13; // di
  int NamedElement; // eax
  int v15; // r9d
  struct DirectUI::Element *v17; // [rsp+30h] [rbp-258h] BYREF
  WCHAR File[264]; // [rsp+40h] [rbp-248h] BYREF

  v5 = 0;
  if ( a1 == 78 )
  {
    v6 = *(_DWORD *)(a3 + 16);
    v7 = *(HWND *)a3;
    if ( v6 != -155 )
    {
      if ( v6 != -101 )
      {
        if ( v6 != -6 && v6 != -5 && v6 != -4 )
        {
          if ( v6 != -3 )
          {
            if ( v6 != -2 )
              return v5;
            return 1;
          }
          SelectedFile = UploadFilePage::GetSelectedFile(a5, File, a3);
          if ( SelectedFile < 0 )
          {
            SdpDebugPrint(1u, "Dwz ERROR: %s:%d - hr = 0x%08X\n", "UploadFilePage::NotifyHandler", 1551, SelectedFile);
            return v5;
          }
          if ( !SelectedFile && (int)ShellExecuteW(0, L"open", File, 0, 0, 1) <= 32 )
          {
            SdpDebugPrint(1u, "Dwz ERROR: %s:%d - hr = 0x%08X\n", "UploadFilePage::NotifyHandler", 1567, -2147467259);
            return v5;
          }
        }
        return 1;
      }
      v9 = SendMessageW(v7, 0x1004u, 0, 0);
      for ( i = 0; i < v9; v5 = v12 )
      {
        v11 = SendMessageW(v7, 0x102Cu, i, 61440);
        v12 = v5 + 1;
        if ( (v11 & 0xFFFFF000) == 0x1000 )
          v12 = v5;
        ++i;
      }
      DirectUI::TaskPage::PropSheet_SendMessage(a5, 0x48Bu, -(__int64)(v5 != 0) & 2, 2);
      v17 = 0;
      v13 = (unsigned int)SendMessageW(v7, 0x1032u, 0, 0) == 1;
      NamedElement = WizardPage::GetNamedElement(a5, L"btnView", &v17);
      if ( NamedElement >= 0 )
      {
        NamedElement = DirectUI::Element::SetEnabled(v17, v13);
        if ( NamedElement >= 0 )
          return 1;
        v15 = 1700;
      }
      else
      {
        v15 = 1697;
      }
      SdpDebugPrint(1u, "Dwz ERROR: %s:%d - hr = 0x%08X\n", "UploadFilePage::EnableViewButton", v15, NamedElement);
      return 1;
    }
    if ( *(_WORD *)(a3 + 24) == 67 && GetKeyState(17) < 0 )
    {
      UploadFilePage::Copy(a5, v7);
      return 1;
    }
  }
  return v5;
}

```

## disassembly

```asm
0x14003a760  mov     [rsp+arg_0], rbx
0x14003a765  mov     [rsp+arg_8], rbp
0x14003a76a  push    rsi
0x14003a76b  push    rdi
0x14003a76c  push    r12
0x14003a76e  push    r14
0x14003a770  push    r15
0x14003a772  sub     rsp, 260h
0x14003a779  mov     rax, cs:__security_cookie
0x14003a780  xor     rax, rsp
0x14003a783  mov     [rsp+288h+var_38], rax
0x14003a78b  mov     r14, [rsp+288h+arg_20]
0x14003a793  xor     r12d, r12d
0x14003a796  mov     edi, r12d
0x14003a799  cmp     ecx, 4Eh ; 'N'
0x14003a79c  jnz     loc_14003A997
0x14003a7a2  mov     eax, [r8+10h]
0x14003a7a6  mov     rsi, [r8]
0x14003a7a9  cmp     eax, 0FFFFFF65h
0x14003a7ae  jz      loc_14003A969
0x14003a7b4  lea     ebx, [rcx-4Dh]
0x14003a7b7  cmp     eax, 0FFFFFF9Bh
0x14003a7ba  jz      loc_14003A868
0x14003a7c0  cmp     eax, 0FFFFFFFAh
0x14003a7c3  jz      loc_14003A965
0x14003a7c9  cmp     eax, 0FFFFFFFBh
0x14003a7cc  jz      loc_14003A965
0x14003a7d2  cmp     eax, 0FFFFFFFCh
0x14003a7d5  jz      loc_14003A965
0x14003a7db  cmp     eax, 0FFFFFFFDh
0x14003a7de  jz      short loc_14003A7EE
0x14003a7e0  cmp     eax, 0FFFFFFFEh
0x14003a7e3  jz      loc_14003A965
0x14003a7e9  jmp     loc_14003A997
0x14003a7ee  lea     rdx, [rsp+288h+File]; unsigned __int16 *
0x14003a7f3  mov     rcx, r14; this
0x14003a7f6  call    ?GetSelectedFile@UploadFilePage@@IEAAJPEAG_K@Z; UploadFilePage::GetSelectedFile(ushort *,unsigned __int64)
0x14003a7fb  test    eax, eax
0x14003a7fd  jns     short loc_14003A823
0x14003a7ff  mov     dword ptr [rsp+288h+lpDirectory], eax
0x14003a803  mov     r9d, 60Fh
0x14003a809  lea     r8, aUploadfilepage_6; "UploadFilePage::NotifyHandler"
0x14003a810  mov     ecx, ebx; Level
0x14003a812  lea     rdx, aDwzErrorSDHr0x; "Dwz ERROR: %s:%d - hr = 0x%08X\n"
0x14003a819  call    ?SdpDebugPrint@@YAXKPEBDZZ; SdpDebugPrint(ulong,char const *,...)
0x14003a81e  jmp     loc_14003A997
0x14003a823  jnz     loc_14003A965
0x14003a829  mov     [rsp+288h+nShowCmd], ebx; nShowCmd
0x14003a82d  lea     r8, [rsp+288h+File]; lpFile
0x14003a832  xor     r9d, r9d; lpParameters
0x14003a835  mov     [rsp+288h+lpDirectory], r12; lpDirectory
0x14003a83a  lea     rdx, Operation; "open"
0x14003a841  xor     ecx, ecx; hwnd
0x14003a843  call    cs:__imp_ShellExecuteW
0x14003a84a  nop     dword ptr [rax+rax+00h]
0x14003a84f  cmp     eax, 20h ; ' '
0x14003a852  jg      loc_14003A965
0x14003a858  mov     dword ptr [rsp+288h+lpDirectory], 80004005h
0x14003a860  mov     r9d, 61Fh
0x14003a866  jmp     short loc_14003A809
0x14003a868  xor     r9d, r9d; lParam
0x14003a86b  xor     r8d, r8d; wParam
0x14003a86e  mov     edx, 1004h; Msg
0x14003a873  mov     rcx, rsi; hWnd
0x14003a876  call    cs:__imp_SendMessageW
0x14003a87d  nop     dword ptr [rax+rax+00h]
0x14003a882  mov     r15, rax
0x14003a885  mov     ebp, r12d
0x14003a888  test    eax, eax
0x14003a88a  jz      short loc_14003A8C2
0x14003a88c  mov     r8d, ebp; wParam
0x14003a88f  mov     edx, 102Ch; Msg
0x14003a894  mov     r9d, 0F000h; lParam
0x14003a89a  mov     rcx, rsi; hWnd
0x14003a89d  call    cs:__imp_SendMessageW
0x14003a8a4  nop     dword ptr [rax+rax+00h]
0x14003a8a9  and     eax, 0FFFFF000h
0x14003a8ae  lea     ecx, [rdi+1]
0x14003a8b1  cmp     eax, 1000h
0x14003a8b6  cmovz   ecx, edi
0x14003a8b9  add     ebp, ebx
0x14003a8bb  mov     edi, ecx
0x14003a8bd  cmp     ebp, r15d
0x14003a8c0  jb      short loc_14003A88C
0x14003a8c2  mov     eax, r12d
0x14003a8c5  mov     r9d, 2
0x14003a8cb  sub     eax, edi
0x14003a8cd  mov     edx, 48Bh
0x14003a8d2  neg     eax
0x14003a8d4  mov     rcx, r14
0x14003a8d7  sbb     r8, r8
0x14003a8da  and     r8, r9
0x14003a8dd  call    cs:__imp_?PropSheet_SendMessage@TaskPage@DirectUI@@IEAA_JI_K_J@Z; DirectUI::TaskPage::PropSheet_SendMessage(uint,unsigned __int64,__int64)
0x14003a8e4  nop     dword ptr [rax+rax+00h]
0x14003a8e9  xor     r9d, r9d; lParam
0x14003a8ec  xor     r8d, r8d; wParam
0x14003a8ef  mov     edx, 1032h; Msg
0x14003a8f4  mov     rcx, rsi; hWnd
0x14003a8f7  call    cs:__imp_SendMessageW
0x14003a8fe  nop     dword ptr [rax+rax+00h]
0x14003a903  lea     r8, [rsp+288h+var_258]; struct DirectUI::Element **
0x14003a908  mov     [rsp+288h+var_258], r12
0x14003a90d  cmp     eax, ebx
0x14003a90f  lea     rdx, aBtnview; "btnView"
0x14003a916  mov     rcx, r14; this
0x14003a919  setz    dil
0x14003a91d  call    ?GetNamedElement@WizardPage@@QEAAJPEBGPEAPEAVElement@DirectUI@@@Z; WizardPage::GetNamedElement(ushort const *,DirectUI::Element * *)
0x14003a922  test    eax, eax
0x14003a924  jns     short loc_14003A92E
0x14003a926  mov     r9d, 6A1h
0x14003a92c  jmp     short loc_14003A94C
0x14003a92e  mov     rcx, [rsp+288h+var_258]
0x14003a933  mov     dl, dil
0x14003a936  call    cs:__imp_?SetEnabled@Element@DirectUI@@QEAAJ_N@Z; DirectUI::Element::SetEnabled(bool)
0x14003a93d  nop     dword ptr [rax+rax+00h]
0x14003a942  test    eax, eax
0x14003a944  jns     short loc_14003A965
0x14003a946  mov     r9d, 6A4h
0x14003a94c  lea     r8, aUploadfilepage_3; "UploadFilePage::EnableViewButton"
0x14003a953  mov     dword ptr [rsp+288h+lpDirectory], eax
0x14003a957  lea     rdx, aDwzErrorSDHr0x; "Dwz ERROR: %s:%d - hr = 0x%08X\n"
0x14003a95e  mov     ecx, ebx; Level
0x14003a960  call    ?SdpDebugPrint@@YAXKPEBDZZ; SdpDebugPrint(ulong,char const *,...)
0x14003a965  mov     edi, ebx
0x14003a967  jmp     short loc_14003A997
0x14003a969  cmp     word ptr [r8+18h], 43h ; 'C'
0x14003a96f  jnz     short loc_14003A997
0x14003a971  mov     ecx, 11h; nVirtKey
0x14003a976  call    cs:__imp_GetKeyState
0x14003a97d  nop     dword ptr [rax+rax+00h]
0x14003a982  test    ax, ax
0x14003a985  jns     short loc_14003A997
0x14003a987  mov     rdx, rsi; hWndNewOwner
0x14003a98a  mov     rcx, r14; this
0x14003a98d  call    ?Copy@UploadFilePage@@IEAAJPEAUHWND__@@@Z; UploadFilePage::Copy(HWND__ *)
0x14003a992  mov     edi, 1
0x14003a997  mov     eax, edi
0x14003a999  mov     rcx, [rsp+288h+var_38]
0x14003a9a1  xor     rcx, rsp; StackCookie
0x14003a9a4  call    __security_check_cookie
0x14003a9a9  lea     r11, [rsp+288h+var_28]
0x14003a9b1  mov     rbx, [r11+30h]
0x14003a9b5  mov     rbp, [r11+38h]
0x14003a9b9  mov     rsp, r11
0x14003a9bc  pop     r15
0x14003a9be  pop     r14
0x14003a9c0  pop     r12
0x14003a9c2  pop     rdi
0x14003a9c3  pop     rsi
0x14003a9c4  retn
```
