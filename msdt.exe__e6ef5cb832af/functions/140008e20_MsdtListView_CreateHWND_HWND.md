# MsdtListView::CreateHWND(HWND__ *)

- ea: `0x140008e20`
- end: `0x140008e75`
- name: `?CreateHWND@MsdtListView@@MEAAPEAUHWND__@@PEAU2@@Z`
- size: `85`
- prototype: `HWND __fastcall(MsdtListView *__hidden this, HWND)`
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `USER32!SendMessageW` at `0x140008e5f`
- `USER32!SendMessageW` at `0x140008e5f`
- `UxTheme!SetWindowTheme` at `0x140008e42`
- `UxTheme!SetWindowTheme` at `0x140008e42`
- `DUI70!?CreateHWND@CCBase@DirectUI@@UEAAPEAUHWND__@@PEAU3@@Z` at `0x140008e26`
- `DUI70!?CreateHWND@CCBase@DirectUI@@UEAAPEAUHWND__@@PEAU3@@Z` at `0x140008e26`

## pseudocode

```c
HWND __fastcall MsdtListView::CreateHWND(MsdtListView *this, HWND a2)
{
  HWND HWND; // rbx

  HWND = DirectUI::CCBase::CreateHWND(this, a2);
  SetWindowTheme(HWND, L"Explorer", 0);
  SendMessageW(HWND, 0x1036u, 0x10000u, 0x10000);
  return HWND;
}

```

## disassembly

```asm
0x140008e20  push    rbx
0x140008e22  sub     rsp, 20h
0x140008e26  call    cs:__imp_?CreateHWND@CCBase@DirectUI@@UEAAPEAUHWND__@@PEAU3@@Z; DirectUI::CCBase::CreateHWND(HWND__ *)
0x140008e2d  nop     dword ptr [rax+rax+00h]
0x140008e32  xor     r8d, r8d; pszSubIdList
0x140008e35  lea     rdx, pszSubAppName; "Explorer"
0x140008e3c  mov     rcx, rax; hwnd
0x140008e3f  mov     rbx, rax
0x140008e42  call    cs:__imp_SetWindowTheme
0x140008e49  nop     dword ptr [rax+rax+00h]
0x140008e4e  mov     r8d, 10000h; wParam
0x140008e54  mov     edx, 1036h; Msg
0x140008e59  mov     r9d, r8d; lParam
0x140008e5c  mov     rcx, rbx; hWnd
0x140008e5f  call    cs:__imp_SendMessageW
0x140008e66  nop     dword ptr [rax+rax+00h]
0x140008e6b  mov     rax, rbx
0x140008e6e  add     rsp, 20h
0x140008e72  pop     rbx
0x140008e73  retn
```
