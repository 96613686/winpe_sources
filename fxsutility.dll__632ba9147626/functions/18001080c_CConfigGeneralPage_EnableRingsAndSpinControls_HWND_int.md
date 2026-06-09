# CConfigGeneralPage::EnableRingsAndSpinControls(HWND__ *,int)

- ea: `0x18001080c`
- end: `0x18001085b`
- name: `?EnableRingsAndSpinControls@CConfigGeneralPage@@AEBAKPEAUHWND__@@H@Z`
- size: `79`
- prototype: `unsigned int(CConfigGeneralPage *__hidden this, HWND, int)`
- caller_count: `3`
- callee_count: `0`
- tags: `registry_config`

## callers

- `0x1800107ac`
- `0x180010a84`
- `0x180011040`

## import_xrefs

- `USER32!EnableWindow` at `0x18001082f`
- `USER32!EnableWindow` at `0x180010848`
- `USER32!EnableWindow` at `0x18001082f`
- `USER32!EnableWindow` at `0x180010848`
- `USER32!GetDlgItem` at `0x180010824`
- `USER32!GetDlgItem` at `0x18001083d`
- `USER32!GetDlgItem` at `0x180010824`
- `USER32!GetDlgItem` at `0x18001083d`

## pseudocode

```c
__int64 __fastcall CConfigGeneralPage::EnableRingsAndSpinControls(CConfigGeneralPage *this, HWND a2, BOOL a3)
{
  HWND DlgItem; // rax
  HWND v6; // rax

  DlgItem = GetDlgItem(a2, 4510);
  EnableWindow(DlgItem, a3);
  v6 = GetDlgItem(a2, 4511);
  EnableWindow(v6, a3);
  return 0;
}

```

## disassembly

```asm
0x18001080c  mov     [rsp+arg_0], rbx
0x180010811  push    rdi
0x180010812  sub     rsp, 20h
0x180010816  mov     rbx, rdx
0x180010819  mov     edi, r8d
0x18001081c  mov     rcx, rbx; hDlg
0x18001081f  mov     edx, 119Eh; nIDDlgItem
0x180010824  call    cs:__imp_GetDlgItem
0x18001082a  mov     rcx, rax; hWnd
0x18001082d  mov     edx, edi; bEnable
0x18001082f  call    cs:__imp_EnableWindow
0x180010835  mov     edx, 119Fh; nIDDlgItem
0x18001083a  mov     rcx, rbx; hDlg
0x18001083d  call    cs:__imp_GetDlgItem
0x180010843  mov     rcx, rax; hWnd
0x180010846  mov     edx, edi; bEnable
0x180010848  call    cs:__imp_EnableWindow
0x18001084e  mov     rbx, [rsp+28h+arg_0]
0x180010853  xor     eax, eax
0x180010855  add     rsp, 20h
0x180010859  pop     rdi
0x18001085a  retn
```
