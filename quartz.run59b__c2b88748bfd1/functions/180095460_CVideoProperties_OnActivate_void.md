# CVideoProperties::OnActivate(void)

- ea: `0x180095460`
- end: `0x180095551`
- name: `?OnActivate@CVideoProperties@@UEAAJXZ`
- size: `241`
- prototype: `__int64 __fastcall(CVideoProperties *__hidden this)`
- caller_count: `0`
- callee_count: `4`
- tags: `installer_update`

## callees

- `0x1800388a0`
- `0x180039250`
- `0x180095ae8`
- `0x180095e98`

## import_xrefs

- `GDI32!CreateFontIndirectW` at `0x1800954b9`
- `GDI32!CreateFontIndirectW` at `0x1800954b9`
- `USER32!SystemParametersInfoW` at `0x1800954a5`
- `USER32!SystemParametersInfoW` at `0x1800954a5`
- `USER32!SendMessageW` at `0x1800954f0`
- `USER32!SendMessageW` at `0x180095514`
- `USER32!SendMessageW` at `0x1800954f0`
- `USER32!SendMessageW` at `0x180095514`
- `USER32!GetDlgItem` at `0x1800954d5`
- `USER32!GetDlgItem` at `0x1800954d5`

## pseudocode

```c
__int64 __fastcall CVideoProperties::OnActivate(CVideoProperties *this)
{
  HFONT v2; // rax
  HWND v3; // rcx
  HWND DlgItem; // rax
  int pvParam; // [rsp+20h] [rbp-218h] BYREF
  _BYTE v7[312]; // [rsp+24h] [rbp-214h] BYREF
  LOGFONTW lf; // [rsp+15Ch] [rbp-DCh] BYREF

  memset_0(v7, 0, 0x1F4u);
  pvParam = 504;
  SystemParametersInfoW(0x29u, 0x1F8u, &pvParam, 0);
  v2 = CreateFontIndirectW(&lf);
  v3 = (HWND)*((_QWORD *)this + 6);
  *((_QWORD *)this + 74) = v2;
  DlgItem = GetDlgItem(v3, 109);
  SendMessageW(DlgItem, 0xF1u, 1u, 0);
  SendMessageW(*((HWND *)this + 75), 0x30u, *((_QWORD *)this + 74), 1);
  CVideoProperties::UpdateListBox(this, 0x6Du);
  CVideoProperties::SetDrawSwitches(this);
  return 0;
}

```

## disassembly

```asm
0x180095460  push    rbx
0x180095462  sub     rsp, 230h
0x180095469  mov     rax, cs:__security_cookie
0x180095470  xor     rax, rsp
0x180095473  mov     [rsp+238h+var_18], rax
0x18009547b  mov     rbx, rcx
0x18009547e  xor     edx, edx; Val
0x180095480  lea     rcx, [rsp+238h+var_214]; void *
0x180095485  mov     r8d, 1F4h; Size
0x18009548b  call    memset_0
0x180095490  xor     r9d, r9d; fWinIni
0x180095493  lea     r8, [rsp+238h+pvParam]; pvParam
0x180095498  mov     edx, 1F8h; uiParam
0x18009549d  mov     [rsp+238h+pvParam], edx
0x1800954a1  lea     ecx, [r9+29h]; uiAction
0x1800954a5  call    cs:__imp_SystemParametersInfoW
0x1800954ac  nop     dword ptr [rax+rax+00h]
0x1800954b1  lea     rcx, [rsp+238h+lf]; lplf
0x1800954b9  call    cs:__imp_CreateFontIndirectW
0x1800954c0  nop     dword ptr [rax+rax+00h]
0x1800954c5  mov     rcx, [rbx+30h]; hDlg
0x1800954c9  mov     edx, 6Dh ; 'm'; nIDDlgItem
0x1800954ce  mov     [rbx+250h], rax
0x1800954d5  call    cs:__imp_GetDlgItem
0x1800954dc  nop     dword ptr [rax+rax+00h]
0x1800954e1  xor     r9d, r9d; lParam
0x1800954e4  mov     edx, 0F1h; Msg
0x1800954e9  mov     rcx, rax; hWnd
0x1800954ec  lea     r8d, [r9+1]; wParam
0x1800954f0  call    cs:__imp_SendMessageW
0x1800954f7  nop     dword ptr [rax+rax+00h]
0x1800954fc  mov     r8, [rbx+250h]; wParam
0x180095503  mov     r9d, 1; lParam
0x180095509  mov     rcx, [rbx+258h]; hWnd
0x180095510  lea     edx, [r9+2Fh]; Msg
0x180095514  call    cs:__imp_SendMessageW
0x18009551b  nop     dword ptr [rax+rax+00h]
0x180095520  mov     edx, 6Dh ; 'm'; unsigned int
0x180095525  mov     rcx, rbx; this
0x180095528  call    ?UpdateListBox@CVideoProperties@@AEAAXK@Z; CVideoProperties::UpdateListBox(ulong)
0x18009552d  mov     rcx, rbx; this
0x180095530  call    ?SetDrawSwitches@CVideoProperties@@AEAAXXZ; CVideoProperties::SetDrawSwitches(void)
0x180095535  xor     eax, eax
0x180095537  mov     rcx, [rsp+238h+var_18]
0x18009553f  xor     rcx, rsp; StackCookie
0x180095542  call    __security_check_cookie
0x180095547  add     rsp, 230h
0x18009554e  pop     rbx
0x18009554f  retn
```
