# Spin_Enable(HWND__ *,int,ushort)

- ea: `0x18001347c`
- end: `0x1800134fc`
- name: `?Spin_Enable@@YAXPEAUHWND__@@HG@Z`
- size: `128`
- prototype: `void __fastcall(HWND hDlg, int nIDDlgItem, unsigned __int16)`
- caller_count: `5`
- callee_count: `0`
- tags: ``

## callers

- `0x180013c28`
- `0x180014aa0`
- `0x180017510`
- `0x180017680`
- `0x180018780`

## import_xrefs

- `USER32!EnableWindow` at `0x1800134b4`
- `USER32!EnableWindow` at `0x1800134cd`
- `USER32!EnableWindow` at `0x1800134b4`
- `USER32!EnableWindow` at `0x1800134cd`
- `USER32!GetDlgItem` at `0x1800134bf`
- `USER32!GetDlgItem` at `0x1800134bf`
- `USER32!SendDlgItemMessageW` at `0x1800134a6`
- `USER32!SendDlgItemMessageW` at `0x1800134e6`
- `USER32!SendDlgItemMessageW` at `0x1800134a6`
- `USER32!SendDlgItemMessageW` at `0x1800134e6`

## pseudocode

```c
void __fastcall Spin_Enable(HWND hDlg, int nIDDlgItem, unsigned __int16 a3)
{
  LPARAM lParam; // rbx
  HWND v6; // rax
  HWND DlgItem; // rax

  lParam = a3;
  v6 = (HWND)SendDlgItemMessageW(hDlg, nIDDlgItem, 0x46Au, 0, 0);
  EnableWindow(v6, 1);
  DlgItem = GetDlgItem(hDlg, nIDDlgItem);
  EnableWindow(DlgItem, 1);
  SendDlgItemMessageW(hDlg, nIDDlgItem, 0x467u, 0, lParam);
}

```

## disassembly

```asm
0x18001347c  mov     [rsp+arg_0], rbx
0x180013481  mov     [rsp+arg_8], rsi
0x180013486  push    rdi
0x180013487  sub     rsp, 30h
0x18001348b  movzx   ebx, r8w
0x18001348f  xor     r9d, r9d; wParam
0x180013492  mov     r8d, 46Ah; Msg
0x180013498  mov     [rsp+38h+lParam], 0; lParam
0x1800134a1  mov     edi, edx
0x1800134a3  mov     rsi, rcx
0x1800134a6  call    cs:__imp_SendDlgItemMessageW
0x1800134ac  mov     rcx, rax; hWnd
0x1800134af  mov     edx, 1; bEnable
0x1800134b4  call    cs:__imp_EnableWindow
0x1800134ba  mov     edx, edi; nIDDlgItem
0x1800134bc  mov     rcx, rsi; hDlg
0x1800134bf  call    cs:__imp_GetDlgItem
0x1800134c5  mov     rcx, rax; hWnd
0x1800134c8  mov     edx, 1; bEnable
0x1800134cd  call    cs:__imp_EnableWindow
0x1800134d3  xor     r9d, r9d; wParam
0x1800134d6  mov     [rsp+38h+lParam], rbx; lParam
0x1800134db  mov     r8d, 467h; Msg
0x1800134e1  mov     edx, edi; nIDDlgItem
0x1800134e3  mov     rcx, rsi; hDlg
0x1800134e6  call    cs:__imp_SendDlgItemMessageW
0x1800134ec  mov     rbx, [rsp+38h+arg_0]
0x1800134f1  mov     rsi, [rsp+38h+arg_8]
0x1800134f6  add     rsp, 30h
0x1800134fa  pop     rdi
0x1800134fb  retn
```
