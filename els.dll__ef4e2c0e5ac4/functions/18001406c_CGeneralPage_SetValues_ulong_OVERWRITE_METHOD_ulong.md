# CGeneralPage::_SetValues(ulong,OVERWRITE_METHOD,ulong)

- ea: `0x18001406c`
- end: `0x180014121`
- name: `?_SetValues@CGeneralPage@@IEAAXKW4OVERWRITE_METHOD@@K@Z`
- size: `181`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x1800135d0`
- `0x180013810`

## callees

- `0x180013028`

## import_xrefs

- `USER32!SetDlgItemInt` at `0x18001408e`
- `USER32!SetDlgItemInt` at `0x1800140a3`
- `USER32!SetDlgItemInt` at `0x18001408e`
- `USER32!SetDlgItemInt` at `0x1800140a3`
- `USER32!SendMessageW` at `0x1800140c6`
- `USER32!SendMessageW` at `0x1800140ed`
- `USER32!SendMessageW` at `0x1800140c6`
- `USER32!SendMessageW` at `0x1800140ed`
- `USER32!GetDlgItem` at `0x1800140b2`
- `USER32!GetDlgItem` at `0x1800140d8`
- `USER32!GetDlgItem` at `0x1800140b2`
- `USER32!GetDlgItem` at `0x1800140d8`
- `USER32!CheckRadioButton` at `0x180014103`
- `USER32!CheckRadioButton` at `0x180014103`

## pseudocode

```c
void __fastcall CGeneralPage::_SetValues(__int64 a1, UINT a2, int a3, UINT a4)
{
  HWND DlgItem; // rax
  HWND v9; // rcx
  HWND v10; // rax

  SetDlgItemInt(*(HWND *)(a1 + 16), 125, a2, 0);
  SetDlgItemInt(*(HWND *)(a1 + 16), 130, a4, 0);
  DlgItem = GetDlgItem(*(HWND *)(a1 + 16), 127);
  SendMessageW(DlgItem, 0x467u, 0, 0);
  v9 = *(HWND *)(a1 + 16);
  *(_DWORD *)(a1 + 64) = a2;
  v10 = GetDlgItem(v9, 131);
  SendMessageW(v10, 0x467u, 0, (unsigned __int16)a4);
  CheckRadioButton(*(HWND *)(a1 + 16), 122, 124, a3);
  CGeneralPage::_EnableOlderThanCtrls((CGeneralPage *)a1, a3 == 123);
}

```

## disassembly

```asm
0x18001406c  push    rbx
0x18001406e  push    rbp
0x18001406f  push    rsi
0x180014070  push    rdi
0x180014071  sub     rsp, 28h
0x180014075  mov     edi, r9d
0x180014078  mov     esi, r8d
0x18001407b  xor     r9d, r9d; bSigned
0x18001407e  mov     ebx, edx
0x180014080  mov     rbp, rcx
0x180014083  mov     r8d, edx; uValue
0x180014086  mov     rcx, [rcx+10h]; hDlg
0x18001408a  lea     edx, [r9+7Dh]; nIDDlgItem
0x18001408e  call    cs:__imp_SetDlgItemInt
0x180014094  mov     rcx, [rbp+10h]; hDlg
0x180014098  xor     r9d, r9d; bSigned
0x18001409b  mov     r8d, edi; uValue
0x18001409e  mov     edx, 82h; nIDDlgItem
0x1800140a3  call    cs:__imp_SetDlgItemInt
0x1800140a9  mov     rcx, [rbp+10h]; hDlg
0x1800140ad  mov     edx, 7Fh; nIDDlgItem
0x1800140b2  call    cs:__imp_GetDlgItem
0x1800140b8  xor     r9d, r9d; lParam
0x1800140bb  xor     r8d, r8d; wParam
0x1800140be  mov     rcx, rax; hWnd
0x1800140c1  mov     edx, 467h; Msg
0x1800140c6  call    cs:__imp_SendMessageW
0x1800140cc  mov     rcx, [rbp+10h]; hDlg
0x1800140d0  mov     edx, 83h; nIDDlgItem
0x1800140d5  mov     [rbp+40h], ebx
0x1800140d8  call    cs:__imp_GetDlgItem
0x1800140de  movzx   r9d, di; lParam
0x1800140e2  xor     r8d, r8d; wParam
0x1800140e5  mov     rcx, rax; hWnd
0x1800140e8  mov     edx, 467h; Msg
0x1800140ed  call    cs:__imp_SendMessageW
0x1800140f3  mov     rcx, [rbp+10h]; hDlg
0x1800140f7  mov     edx, 7Ah ; 'z'; nIDFirstButton
0x1800140fc  mov     r9d, esi; nIDCheckButton
0x1800140ff  lea     r8d, [rdx+2]; nIDLastButton
0x180014103  call    cs:__imp_CheckRadioButton
0x180014109  xor     edx, edx
0x18001410b  mov     rcx, rbp; this
0x18001410e  cmp     esi, 7Bh ; '{'
0x180014111  setz    dl; int
0x180014114  add     rsp, 28h
0x180014118  pop     rdi
0x180014119  pop     rsi
0x18001411a  pop     rbp
0x18001411b  pop     rbx
0x18001411c  jmp     ?_EnableOlderThanCtrls@CGeneralPage@@IEAAXH@Z; CGeneralPage::_EnableOlderThanCtrls(int)
```
