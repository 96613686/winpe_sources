# MsdtEdit::CreateHWND(HWND__ *)

- ea: `0x140008d50`
- end: `0x140008e18`
- name: `?CreateHWND@MsdtEdit@@MEAAPEAUHWND__@@PEAU2@@Z`
- size: `200`
- prototype: `HWND(MsdtEdit *__hidden this, HWND)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x140008d50`

## import_xrefs

- `USER32!CreateWindowExW` at `0x140008de1`
- `USER32!CreateWindowExW` at `0x140008de1`
- `DUI70!?AttachCtrlSubclassProc@HWNDHost@DirectUI@@KAXPEAUHWND__@@@Z` at `0x140008df8`
- `DUI70!?AttachCtrlSubclassProc@HWNDHost@DirectUI@@KAXPEAUHWND__@@@Z` at `0x140008df8`
- `DUI70!?GetThemedBorder@Edit@DirectUI@@QEAA_NXZ` at `0x140008d7e`
- `DUI70!?GetThemedBorder@Edit@DirectUI@@QEAA_NXZ` at `0x140008d7e`
- `DUI70!?GetMultiline@Edit@DirectUI@@QEAA_NXZ` at `0x140008d65`
- `DUI70!?GetMultiline@Edit@DirectUI@@QEAA_NXZ` at `0x140008d65`

## pseudocode

```c
HWND __fastcall MsdtEdit::CreateHWND(MsdtEdit *this, HWND a2)
{
  int v4; // edi
  bool ThemedBorder; // al
  HWND Window; // rax
  HWND v7; // rbx

  v4 = DirectUI::Edit::GetMultiline(this) ? 0x200F84 : 0;
  ThemedBorder = DirectUI::Edit::GetThemedBorder(this);
  Window = CreateWindowExW((unsigned __int8)ThemedBorder << 9, L"edit", 0, v4 + 1342177408, 0, 0, 0, 0, a2, 0, 0, 0);
  v7 = Window;
  if ( Window )
    DirectUI::HWNDHost::AttachCtrlSubclassProc(Window);
  return v7;
}

```

## disassembly

```asm
0x140008d50  mov     [rsp+arg_0], rbx
0x140008d55  mov     [rsp+arg_8], rsi
0x140008d5a  push    rdi
0x140008d5b  sub     rsp, 60h
0x140008d5f  mov     rsi, rdx
0x140008d62  mov     rbx, rcx
0x140008d65  call    cs:__imp_?GetMultiline@Edit@DirectUI@@QEAA_NXZ; DirectUI::Edit::GetMultiline(void)
0x140008d6c  nop     dword ptr [rax+rax+00h]
0x140008d71  neg     al
0x140008d73  mov     rcx, rbx
0x140008d76  sbb     edi, edi
0x140008d78  and     edi, 200F84h
0x140008d7e  call    cs:__imp_?GetThemedBorder@Edit@DirectUI@@QEAA_NXZ; DirectUI::Edit::GetThemedBorder(void)
0x140008d85  nop     dword ptr [rax+rax+00h]
0x140008d8a  mov     [rsp+68h+lpParam], 0; lpParam
0x140008d93  lea     r9d, [rdi+50000080h]; dwStyle
0x140008d9a  mov     [rsp+68h+hInstance], 0; hInstance
0x140008da3  lea     rdx, ClassName; "edit"
0x140008daa  mov     [rsp+68h+hMenu], 0; hMenu
0x140008db3  xor     r8d, r8d; lpWindowName
0x140008db6  mov     [rsp+68h+hWndParent], rsi; hWndParent
0x140008dbb  mov     [rsp+68h+nHeight], 0; nHeight
0x140008dc3  movzx   ecx, al
0x140008dc6  mov     [rsp+68h+nWidth], 0; nWidth
0x140008dce  mov     [rsp+68h+Y], 0; Y
0x140008dd6  shl     ecx, 9; dwExStyle
0x140008dd9  mov     [rsp+68h+X], 0; X
0x140008de1  call    cs:__imp_CreateWindowExW
0x140008de8  nop     dword ptr [rax+rax+00h]
0x140008ded  mov     rbx, rax
0x140008df0  test    rax, rax
0x140008df3  jz      short loc_140008E04
0x140008df5  mov     rcx, rax
0x140008df8  call    cs:__imp_?AttachCtrlSubclassProc@HWNDHost@DirectUI@@KAXPEAUHWND__@@@Z; DirectUI::HWNDHost::AttachCtrlSubclassProc(HWND__ *)
0x140008dff  nop     dword ptr [rax+rax+00h]
0x140008e04  mov     rsi, [rsp+68h+arg_8]
0x140008e09  mov     rax, rbx
0x140008e0c  mov     rbx, [rsp+68h+arg_0]
0x140008e11  add     rsp, 60h
0x140008e15  pop     rdi
0x140008e16  retn
```
