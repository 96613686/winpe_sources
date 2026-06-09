# CIntlAdvancedDlg::_CopySettings_InitListView(HWND__ *)

- ea: `0x180009a14`
- end: `0x180009aa4`
- name: `?_CopySettings_InitListView@CIntlAdvancedDlg@@AEAAHPEAUHWND__@@@Z`
- size: `144`
- prototype: `__int64 __fastcall(CIntlAdvancedDlg *__hidden this, HWND)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, installer_update`

## callers

- `0x180009870`

## callees

- `0x1800028c4`
- `0x180008a48`
- `0x180008af0`
- `0x180008c34`
- `0x180009a14`
- `0x180009b5c`
- `0x180009ca0`

## import_xrefs

- `USER32!GetDlgItem` at `0x180009a2d`
- `USER32!GetDlgItem` at `0x180009a2d`

## pseudocode

```c
__int64 __fastcall CIntlAdvancedDlg::_CopySettings_InitListView(CIntlAdvancedDlg *this, HWND a2)
{
  unsigned int v4; // ebx
  HWND DlgItem; // rdi
  HWND *v6; // rax
  CAccountListView *v7; // rdi

  v4 = 0;
  DlgItem = GetDlgItem(a2, 2110);
  if ( DlgItem )
  {
    v6 = (HWND *)operator new(0xC88u);
    if ( v6 )
      *v6 = DlgItem;
    *((_QWORD *)this + 2) = v6;
    if ( v6 )
    {
      CIntlAdvancedDlg::_CopySettings_SetListViewData(this);
      v7 = (CAccountListView *)*((_QWORD *)this + 2);
      if ( (unsigned int)CAccountListView::_InitStrings(v7) )
      {
        CAccountListView::_InitStyles(v7);
        CAccountListView::_InitRows(v7);
        v4 = 1;
      }
      CIntlAdvancedDlg::_CopySettings_UpdateListView((CAccountListView **)this, a2, 0, 0);
    }
  }
  return v4;
}

```

## disassembly

```asm
0x180009a14  push    rbx
0x180009a16  push    rbp
0x180009a17  push    rsi
0x180009a18  push    rdi
0x180009a19  sub     rsp, 28h
0x180009a1d  mov     rbp, rdx
0x180009a20  mov     rsi, rcx
0x180009a23  mov     rcx, rbp; hDlg
0x180009a26  mov     edx, 83Eh; nIDDlgItem
0x180009a2b  xor     ebx, ebx
0x180009a2d  call    cs:__imp_GetDlgItem
0x180009a33  mov     rdi, rax
0x180009a36  test    rax, rax
0x180009a39  jz      short loc_180009A99
0x180009a3b  mov     ecx, 0C88h; Size
0x180009a40  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180009a45  mov     [rsp+48h+arg_10], rax
0x180009a4a  test    rax, rax
0x180009a4d  jz      short loc_180009A52
0x180009a4f  mov     [rax], rdi
0x180009a52  mov     [rsi+10h], rax
0x180009a56  test    rax, rax
0x180009a59  jz      short loc_180009A99
0x180009a5b  mov     rcx, rsi; this
0x180009a5e  call    ?_CopySettings_SetListViewData@CIntlAdvancedDlg@@AEAAXXZ; CIntlAdvancedDlg::_CopySettings_SetListViewData(void)
0x180009a63  mov     rdi, [rsi+10h]
0x180009a67  mov     rcx, rdi; this
0x180009a6a  call    ?_InitStrings@CAccountListView@@IEAAHXZ; CAccountListView::_InitStrings(void)
0x180009a6f  test    eax, eax
0x180009a71  jz      short loc_180009A88
0x180009a73  mov     rcx, rdi; this
0x180009a76  call    ?_InitStyles@CAccountListView@@IEAAXXZ; CAccountListView::_InitStyles(void)
0x180009a7b  mov     rcx, rdi; this
0x180009a7e  call    ?_InitRows@CAccountListView@@IEAAXXZ; CAccountListView::_InitRows(void)
0x180009a83  mov     ebx, 1
0x180009a88  xor     r9d, r9d; int
0x180009a8b  xor     r8d, r8d; int
0x180009a8e  mov     rdx, rbp; HWND
0x180009a91  mov     rcx, rsi; this
0x180009a94  call    ?_CopySettings_UpdateListView@CIntlAdvancedDlg@@AEAAXPEAUHWND__@@HH@Z; CIntlAdvancedDlg::_CopySettings_UpdateListView(HWND__ *,int,int)
0x180009a99  mov     eax, ebx
0x180009a9b  add     rsp, 28h
0x180009a9f  pop     rdi
0x180009aa0  pop     rsi
0x180009aa1  pop     rbp
0x180009aa2  pop     rbx
0x180009aa3  retn
```
