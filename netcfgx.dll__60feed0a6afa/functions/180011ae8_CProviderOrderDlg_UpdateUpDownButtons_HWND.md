# CProviderOrderDlg::UpdateUpDownButtons(HWND__ *)

- ea: `0x180011ae8`
- end: `0x180011c30`
- name: `?UpdateUpDownButtons@CProviderOrderDlg@@AEAAJPEAUHWND__@@@Z`
- size: `328`
- prototype: `int(CProviderOrderDlg *__hidden this, HWND)`
- caller_count: `2`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x180011270`
- `0x1800116b0`

## callees

- `0x180011ae8`
- `0x1800120d8`

## import_xrefs

- `USER32!SendMessageW` at `0x180011b41`
- `USER32!SendMessageW` at `0x180011b60`
- `USER32!SendMessageW` at `0x180011b7a`
- `USER32!SendMessageW` at `0x180011b98`
- `USER32!SendMessageW` at `0x180011b41`
- `USER32!SendMessageW` at `0x180011b60`
- `USER32!SendMessageW` at `0x180011b7a`
- `USER32!SendMessageW` at `0x180011b98`
- `USER32!GetDlgItem` at `0x180011b08`
- `USER32!GetDlgItem` at `0x180011b1a`
- `USER32!GetDlgItem` at `0x180011b08`
- `USER32!GetDlgItem` at `0x180011b1a`
- `USER32!SetFocus` at `0x180011bf0`
- `USER32!SetFocus` at `0x180011bf0`
- `USER32!GetFocus` at `0x180011b23`
- `USER32!GetFocus` at `0x180011b23`
- `USER32!EnableWindow` at `0x180011c0a`
- `USER32!EnableWindow` at `0x180011c17`
- `USER32!EnableWindow` at `0x180011c0a`
- `USER32!EnableWindow` at `0x180011c17`

## pseudocode

```c
__int64 __fastcall CProviderOrderDlg::UpdateUpDownButtons(HWND *this, HWND a2)
{
  HWND DlgItem; // r15
  HWND v5; // r14
  HWND Focus; // r12
  bool v7; // si
  bool v8; // di
  LRESULT v9; // rax
  LPARAM v10; // r13
  int v11; // edx

  DlgItem = GetDlgItem(this[1], 25012);
  v5 = GetDlgItem(this[1], 25013);
  Focus = GetFocus();
  v7 = 0;
  v8 = 0;
  v9 = SendMessageW(a2, 0x110Au, 9u, 0);
  v10 = v9;
  if ( v9 && !SendMessageW(a2, 0x110Au, 4u, v9) )
  {
    v8 = SendMessageW(a2, 0x110Au, 2u, v10) != 0;
    v7 = SendMessageW(a2, 0x110Au, 1u, v10) != 0;
  }
  if ( Focus != DlgItem || v8 )
  {
    if ( Focus != v5 || v7 )
    {
      SetDefaultButton(this[1], 0);
      goto LABEL_16;
    }
    if ( v8 )
      a2 = DlgItem;
    v11 = v8 ? 0x61B4 : 0;
  }
  else
  {
    if ( v7 )
      a2 = v5;
    v11 = v7 ? 0x61B5 : 0;
  }
  SetDefaultButton(this[1], v11);
  SetFocus(a2);
LABEL_16:
  EnableWindow(DlgItem, v8);
  EnableWindow(v5, v7);
  return 0;
}

```

## disassembly

```asm
0x180011ae8  push    rbx
0x180011aea  push    rbp
0x180011aeb  push    rsi
0x180011aec  push    rdi
0x180011aed  push    r12
0x180011aef  push    r13
0x180011af1  push    r14
0x180011af3  push    r15
0x180011af5  sub     rsp, 28h
0x180011af9  mov     rbx, rdx
0x180011afc  mov     rbp, rcx
0x180011aff  mov     rcx, [rcx+8]; hDlg
0x180011b03  mov     edx, 61B4h; nIDDlgItem
0x180011b08  call    cs:__imp_GetDlgItem
0x180011b0e  mov     rcx, [rbp+8]; hDlg
0x180011b12  mov     edx, 61B5h; nIDDlgItem
0x180011b17  mov     r15, rax
0x180011b1a  call    cs:__imp_GetDlgItem
0x180011b20  mov     r14, rax
0x180011b23  call    cs:__imp_GetFocus
0x180011b29  xor     r9d, r9d; lParam
0x180011b2c  mov     edx, 110Ah; Msg
0x180011b31  mov     rcx, rbx; hWnd
0x180011b34  mov     r12, rax
0x180011b37  xor     sil, sil
0x180011b3a  xor     dil, dil
0x180011b3d  lea     r8d, [r9+9]; wParam
0x180011b41  call    cs:__imp_SendMessageW
0x180011b47  mov     r13, rax
0x180011b4a  test    rax, rax
0x180011b4d  jz      short loc_180011BA6
0x180011b4f  mov     r9, rax; lParam
0x180011b52  mov     edx, 110Ah; Msg
0x180011b57  mov     r8d, 4; wParam
0x180011b5d  mov     rcx, rbx; hWnd
0x180011b60  call    cs:__imp_SendMessageW
0x180011b66  test    rax, rax
0x180011b69  jnz     short loc_180011BA6
0x180011b6b  mov     r9, r13; lParam
0x180011b6e  lea     r8d, [rax+2]; wParam
0x180011b72  mov     edx, 110Ah; Msg
0x180011b77  mov     rcx, rbx; hWnd
0x180011b7a  call    cs:__imp_SendMessageW
0x180011b80  mov     r9, r13; lParam
0x180011b83  mov     edx, 110Ah; Msg
0x180011b88  test    rax, rax
0x180011b8b  mov     r8d, 1; wParam
0x180011b91  mov     rcx, rbx; hWnd
0x180011b94  setnz   dil
0x180011b98  call    cs:__imp_SendMessageW
0x180011b9e  test    rax, rax
0x180011ba1  jz      short loc_180011BA6
0x180011ba3  mov     sil, 1
0x180011ba6  cmp     r12, r15
0x180011ba9  jnz     short loc_180011BC6
0x180011bab  test    dil, dil
0x180011bae  jnz     short loc_180011BC6
0x180011bb0  test    sil, sil
0x180011bb3  mov     al, sil
0x180011bb6  cmovnz  rbx, r14
0x180011bba  neg     al
0x180011bbc  sbb     edx, edx
0x180011bbe  and     edx, 61B5h
0x180011bc4  jmp     short loc_180011BE4
0x180011bc6  cmp     r12, r14
0x180011bc9  jnz     short loc_180011BF8
0x180011bcb  test    sil, sil
0x180011bce  jnz     short loc_180011BF8
0x180011bd0  test    dil, dil
0x180011bd3  mov     al, dil
0x180011bd6  cmovnz  rbx, r15
0x180011bda  neg     al
0x180011bdc  sbb     edx, edx
0x180011bde  and     edx, 61B4h; int
0x180011be4  mov     rcx, [rbp+8]; hDlg
0x180011be8  call    ?SetDefaultButton@@YAXPEAUHWND__@@H@Z; SetDefaultButton(HWND__ *,int)
0x180011bed  mov     rcx, rbx; hWnd
0x180011bf0  call    cs:__imp_SetFocus
0x180011bf6  jmp     short loc_180011C03
0x180011bf8  mov     rcx, [rbp+8]; hDlg
0x180011bfc  xor     edx, edx; int
0x180011bfe  call    ?SetDefaultButton@@YAXPEAUHWND__@@H@Z; SetDefaultButton(HWND__ *,int)
0x180011c03  movzx   edx, dil; bEnable
0x180011c07  mov     rcx, r15; hWnd
0x180011c0a  call    cs:__imp_EnableWindow
0x180011c10  movzx   edx, sil; bEnable
0x180011c14  mov     rcx, r14; hWnd
0x180011c17  call    cs:__imp_EnableWindow
0x180011c1d  xor     eax, eax
0x180011c1f  add     rsp, 28h
0x180011c23  pop     r15
0x180011c25  pop     r14
0x180011c27  pop     r13
0x180011c29  pop     r12
0x180011c2b  pop     rdi
0x180011c2c  pop     rsi
0x180011c2d  pop     rbp
0x180011c2e  pop     rbx
0x180011c2f  retn
```
