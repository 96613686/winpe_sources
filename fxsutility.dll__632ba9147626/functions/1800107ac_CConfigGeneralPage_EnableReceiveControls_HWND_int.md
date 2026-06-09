# CConfigGeneralPage::EnableReceiveControls(HWND__ *,int)

- ea: `0x1800107ac`
- end: `0x180010806`
- name: `?EnableReceiveControls@CConfigGeneralPage@@AEBAKPEAUHWND__@@H@Z`
- size: `90`
- prototype: `unsigned int(CConfigGeneralPage *__hidden this, HWND, int)`
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x180010a84`
- `0x180011040`

## callees

- `0x18001080c`

## import_xrefs

- `USER32!EnableWindow` at `0x1800107cf`
- `USER32!EnableWindow` at `0x1800107e8`
- `USER32!EnableWindow` at `0x1800107cf`
- `USER32!EnableWindow` at `0x1800107e8`
- `USER32!GetDlgItem` at `0x1800107c4`
- `USER32!GetDlgItem` at `0x1800107dd`
- `USER32!GetDlgItem` at `0x1800107c4`
- `USER32!GetDlgItem` at `0x1800107dd`

## pseudocode

```c
__int64 __fastcall CConfigGeneralPage::EnableReceiveControls(CConfigGeneralPage *this, HWND a2, BOOL a3)
{
  HWND DlgItem; // rax
  HWND v6; // rax
  CConfigGeneralPage *v7; // rcx

  DlgItem = GetDlgItem(a2, 4508);
  EnableWindow(DlgItem, a3);
  v6 = GetDlgItem(a2, 4509);
  EnableWindow(v6, a3);
  CConfigGeneralPage::EnableRingsAndSpinControls(v7, a2, a3);
  return 0;
}

```

## disassembly

```asm
0x1800107ac  mov     [rsp+arg_0], rbx
0x1800107b1  push    rdi
0x1800107b2  sub     rsp, 20h
0x1800107b6  mov     rdi, rdx
0x1800107b9  mov     ebx, r8d
0x1800107bc  mov     rcx, rdi; hDlg
0x1800107bf  mov     edx, 119Ch; nIDDlgItem
0x1800107c4  call    cs:__imp_GetDlgItem
0x1800107ca  mov     rcx, rax; hWnd
0x1800107cd  mov     edx, ebx; bEnable
0x1800107cf  call    cs:__imp_EnableWindow
0x1800107d5  mov     edx, 119Dh; nIDDlgItem
0x1800107da  mov     rcx, rdi; hDlg
0x1800107dd  call    cs:__imp_GetDlgItem
0x1800107e3  mov     rcx, rax; hWnd
0x1800107e6  mov     edx, ebx; bEnable
0x1800107e8  call    cs:__imp_EnableWindow
0x1800107ee  mov     r8d, ebx; int
0x1800107f1  mov     rdx, rdi; HWND
0x1800107f4  call    ?EnableRingsAndSpinControls@CConfigGeneralPage@@AEBAKPEAUHWND__@@H@Z; CConfigGeneralPage::EnableRingsAndSpinControls(HWND__ *,int)
0x1800107f9  mov     rbx, [rsp+28h+arg_0]
0x1800107fe  xor     eax, eax
0x180010800  add     rsp, 20h
0x180010804  pop     rdi
0x180010805  retn
```
