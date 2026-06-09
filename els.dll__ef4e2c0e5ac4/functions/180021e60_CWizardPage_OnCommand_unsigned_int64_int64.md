# CWizardPage::_OnCommand(unsigned __int64,__int64)

- ea: `0x180021e60`
- end: `0x180021ef8`
- name: `?_OnCommand@CWizardPage@@EEAAK_K_J@Z`
- size: `152`
- prototype: `unsigned int __fastcall(CWizardPage *__hidden this, unsigned __int64, __int64)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180021c80`
- `0x180021e60`

## import_xrefs

- `USER32!GetDlgItem` at `0x180021e92`
- `USER32!GetDlgItem` at `0x180021eaf`
- `USER32!GetDlgItem` at `0x180021ec5`
- `USER32!GetDlgItem` at `0x180021edf`
- `USER32!GetDlgItem` at `0x180021e92`
- `USER32!GetDlgItem` at `0x180021eaf`
- `USER32!GetDlgItem` at `0x180021ec5`
- `USER32!GetDlgItem` at `0x180021edf`
- `USER32!EnableWindow` at `0x180021ea0`
- `USER32!EnableWindow` at `0x180021ed0`
- `USER32!EnableWindow` at `0x180021eea`
- `USER32!EnableWindow` at `0x180021ea0`
- `USER32!EnableWindow` at `0x180021ed0`
- `USER32!EnableWindow` at `0x180021eea`

## pseudocode

```c
__int64 __fastcall CWizardPage::_OnCommand(HWND *this, __int16 a2)
{
  HWND v3; // rax
  HWND v4; // rax
  BOOL v5; // edx
  HWND DlgItem; // rax

  switch ( a2 )
  {
    case 972:
      DlgItem = GetDlgItem(this[2], 974);
      EnableWindow(DlgItem, 0);
      v4 = GetDlgItem(this[2], 975);
      v5 = 0;
      goto LABEL_7;
    case 973:
      v3 = GetDlgItem(this[2], 974);
      EnableWindow(v3, 1);
      v4 = GetDlgItem(this[2], 975);
      v5 = 1;
LABEL_7:
      EnableWindow(v4, v5);
      return 0;
    case 975:
      CWizardPage::_OnBrowseForMachine((CWizardPage *)this);
      break;
  }
  return 0;
}

```

## disassembly

```asm
0x180021e60  push    rbx
0x180021e62  sub     rsp, 20h
0x180021e66  movzx   r8d, dx
0x180021e6a  mov     rbx, rcx
0x180021e6d  sub     r8d, 3CCh
0x180021e74  jz      short loc_180021EBC
0x180021e76  sub     r8d, 1
0x180021e7a  jz      short loc_180021E89
0x180021e7c  cmp     r8d, 2
0x180021e80  jnz     short loc_180021EF0
0x180021e82  call    ?_OnBrowseForMachine@CWizardPage@@AEAAXXZ; CWizardPage::_OnBrowseForMachine(void)
0x180021e87  jmp     short loc_180021EF0
0x180021e89  mov     rcx, [rcx+10h]; hDlg
0x180021e8d  mov     edx, 3CEh; nIDDlgItem
0x180021e92  call    cs:__imp_GetDlgItem
0x180021e98  mov     rcx, rax; hWnd
0x180021e9b  mov     edx, 1; bEnable
0x180021ea0  call    cs:__imp_EnableWindow
0x180021ea6  mov     rcx, [rbx+10h]; hDlg
0x180021eaa  mov     edx, 3CFh; nIDDlgItem
0x180021eaf  call    cs:__imp_GetDlgItem
0x180021eb5  mov     edx, 1
0x180021eba  jmp     short loc_180021EE7
0x180021ebc  mov     rcx, [rcx+10h]; hDlg
0x180021ec0  mov     edx, 3CEh; nIDDlgItem
0x180021ec5  call    cs:__imp_GetDlgItem
0x180021ecb  mov     rcx, rax; hWnd
0x180021ece  xor     edx, edx; bEnable
0x180021ed0  call    cs:__imp_EnableWindow
0x180021ed6  mov     rcx, [rbx+10h]; hDlg
0x180021eda  mov     edx, 3CFh; nIDDlgItem
0x180021edf  call    cs:__imp_GetDlgItem
0x180021ee5  xor     edx, edx; bEnable
0x180021ee7  mov     rcx, rax; hWnd
0x180021eea  call    cs:__imp_EnableWindow
0x180021ef0  xor     eax, eax
0x180021ef2  add     rsp, 20h
0x180021ef6  pop     rbx
0x180021ef7  retn
```
