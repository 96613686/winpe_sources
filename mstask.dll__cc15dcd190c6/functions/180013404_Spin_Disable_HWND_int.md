# Spin_Disable(HWND__ *,int)

- ea: `0x180013404`
- end: `0x180013474`
- name: `?Spin_Disable@@YAXPEAUHWND__@@H@Z`
- size: `112`
- prototype: `void __fastcall(HWND hDlg, int nIDDlgItem)`
- caller_count: `4`
- callee_count: `0`
- tags: ``

## callers

- `0x180014aa0`
- `0x180017510`
- `0x180017680`
- `0x180018780`

## import_xrefs

- `USER32!EnableWindow` at `0x180013448`
- `USER32!EnableWindow` at `0x180013448`
- `USER32!EnableWindow` at `0x18001346d`
- `USER32!GetDlgItem` at `0x180013453`
- `USER32!GetDlgItem` at `0x180013453`
- `USER32!SendDlgItemMessageW` at `0x18001342a`
- `USER32!SendDlgItemMessageW` at `0x18001342a`
- `USER32!SetWindowTextW` at `0x18001343d`
- `USER32!SetWindowTextW` at `0x18001343d`

## pseudocode

```c
void __fastcall Spin_Disable(HWND hDlg, int nIDDlgItem)
{
  HWND v4; // rbx
  HWND DlgItem; // rax

  v4 = (HWND)SendDlgItemMessageW(hDlg, nIDDlgItem, 0x46Au, 0, 0);
  SetWindowTextW(v4, &String);
  EnableWindow(v4, 0);
  DlgItem = GetDlgItem(hDlg, nIDDlgItem);
  EnableWindow(DlgItem, 0);
}

```

## disassembly

```asm
0x180013404  mov     [rsp+arg_0], rbx
0x180013409  mov     [rsp+arg_8], rsi
0x18001340e  push    rdi
0x18001340f  sub     rsp, 30h
0x180013413  xor     r9d, r9d; wParam
0x180013416  mov     [rsp+38h+lParam], 0; lParam
0x18001341f  mov     r8d, 46Ah; Msg
0x180013425  mov     edi, edx
0x180013427  mov     rsi, rcx
0x18001342a  call    cs:__imp_SendDlgItemMessageW
0x180013430  mov     rcx, rax; hWnd
0x180013433  lea     rdx, String; lpString
0x18001343a  mov     rbx, rax
0x18001343d  call    cs:__imp_SetWindowTextW
0x180013443  xor     edx, edx; bEnable
0x180013445  mov     rcx, rbx; hWnd
0x180013448  call    cs:__imp_EnableWindow
0x18001344e  mov     edx, edi; nIDDlgItem
0x180013450  mov     rcx, rsi; hDlg
0x180013453  call    cs:__imp_GetDlgItem
0x180013459  mov     rcx, rax
0x18001345c  xor     edx, edx
0x18001345e  mov     rbx, [rsp+38h+arg_0]
0x180013463  mov     rsi, [rsp+38h+arg_8]
0x180013468  add     rsp, 30h
0x18001346c  pop     rdi
0x18001346d  jmp     cs:__imp_EnableWindow
```
