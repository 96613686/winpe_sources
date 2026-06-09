# COskOptionsDlg::OnCommand(unsigned __int64)

- ea: `0x140018978`
- end: `0x140018a59`
- name: `?OnCommand@COskOptionsDlg@@AEAAX_K@Z`
- size: `225`
- prototype: `void __fastcall(COskOptionsDlg *__hidden this, unsigned __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x140018db0`

## callees

- `0x140017f94`
- `0x140018978`
- `0x140018b38`

## import_xrefs

- `USER32!DestroyWindow` at `0x140018a48`
- `USER32!DestroyWindow` at `0x140018a48`
- `USER32!SendDlgItemMessageW` at `0x1400189e3`
- `USER32!SendDlgItemMessageW` at `0x140018a23`
- `USER32!SendDlgItemMessageW` at `0x1400189e3`
- `USER32!SendDlgItemMessageW` at `0x140018a23`
- `USER32!GetDlgItem` at `0x1400189fa`
- `USER32!GetDlgItem` at `0x1400189fa`
- `USER32!EnableWindow` at `0x140018a05`
- `USER32!EnableWindow` at `0x140018a05`

## pseudocode

```c
void __fastcall COskOptionsDlg::OnCommand(COskOptionsDlg *this, int a2)
{
  int v3; // edx
  int v4; // edx
  int v5; // edx
  int v6; // edx
  int v7; // edx
  int v8; // edx
  LRESULT v9; // rax
  int v10; // edx
  BOOL v11; // ebx
  HWND DlgItem; // rax
  HWND v13; // rcx

  if ( HIWORD(a2) )
    return;
  v3 = (unsigned __int16)a2 - 1;
  if ( !v3 )
  {
    if ( !COskOptionsDlg::OnOkButtonPressed(this) )
      return;
    v13 = *(HWND *)this;
    goto LABEL_16;
  }
  v4 = v3 - 1;
  if ( !v4 )
  {
    v13 = *(HWND *)this;
LABEL_16:
    DestroyWindow(v13);
    return;
  }
  v5 = v4 - 5010;
  if ( v5 && (v6 = v5 - 1) != 0 && (v7 = v6 - 1) != 0 )
  {
    v8 = v7 - 10;
    if ( v8 )
    {
      if ( v8 != 3 )
        return;
      v9 = SendDlgItemMessageW(*(HWND *)this, 5027, 0xF0u, 0, 0);
      v10 = 5028;
    }
    else
    {
      v9 = SendDlgItemMessageW(*(HWND *)this, 5024, 0xF0u, 0, 0);
      v10 = 5022;
    }
    v11 = v9 == 1;
    DlgItem = GetDlgItem(*(HWND *)this, v10);
    EnableWindow(DlgItem, v11);
  }
  else
  {
    COskOptionsDlg::EnableInputModeUI(this);
  }
}

```

## disassembly

```asm
0x140018978  mov     [rsp+arg_0], rbx
0x14001897d  push    rdi
0x14001897e  sub     rsp, 30h
0x140018982  mov     r8, rdx
0x140018985  xor     eax, eax
0x140018987  shr     r8, 10h
0x14001898b  mov     rdi, rcx
0x14001898e  cmp     ax, r8w
0x140018992  jnz     loc_140018A4E
0x140018998  movzx   edx, dx
0x14001899b  sub     edx, 1
0x14001899e  jz      loc_140018A3C
0x1400189a4  sub     edx, 1
0x1400189a7  jz      loc_140018A37
0x1400189ad  sub     edx, 1392h
0x1400189b3  jz      short loc_140018A30
0x1400189b5  sub     edx, 1
0x1400189b8  jz      short loc_140018A30
0x1400189ba  sub     edx, 1
0x1400189bd  jz      short loc_140018A30
0x1400189bf  sub     edx, 0Ah
0x1400189c2  jz      short loc_140018A0D
0x1400189c4  cmp     edx, 3
0x1400189c7  jnz     loc_140018A4E
0x1400189cd  mov     rcx, [rcx]; hDlg
0x1400189d0  xor     r9d, r9d; wParam
0x1400189d3  mov     edx, 13A3h; nIDDlgItem
0x1400189d8  mov     [rsp+38h+lParam], rax; lParam
0x1400189dd  mov     r8d, 0F0h; Msg
0x1400189e3  call    cs:__imp_SendDlgItemMessageW
0x1400189e9  mov     edx, 13A4h; nIDDlgItem
0x1400189ee  mov     rcx, [rdi]; hDlg
0x1400189f1  xor     ebx, ebx
0x1400189f3  cmp     rax, 1
0x1400189f7  setz    bl
0x1400189fa  call    cs:__imp_GetDlgItem
0x140018a00  mov     rcx, rax; hWnd
0x140018a03  mov     edx, ebx; bEnable
0x140018a05  call    cs:__imp_EnableWindow
0x140018a0b  jmp     short loc_140018A4E
0x140018a0d  mov     rcx, [rcx]; hDlg
0x140018a10  xor     r9d, r9d; wParam
0x140018a13  mov     edx, 13A0h; nIDDlgItem
0x140018a18  mov     [rsp+38h+lParam], rax; lParam
0x140018a1d  mov     r8d, 0F0h; Msg
0x140018a23  call    cs:__imp_SendDlgItemMessageW
0x140018a29  mov     edx, 139Eh
0x140018a2e  jmp     short loc_1400189EE
0x140018a30  call    ?EnableInputModeUI@COskOptionsDlg@@AEAAXXZ; COskOptionsDlg::EnableInputModeUI(void)
0x140018a35  jmp     short loc_140018A4E
0x140018a37  mov     rcx, [rcx]; this
0x140018a3a  jmp     short loc_140018A48
0x140018a3c  call    ?OnOkButtonPressed@COskOptionsDlg@@AEAA_NXZ; COskOptionsDlg::OnOkButtonPressed(void)
0x140018a41  test    al, al
0x140018a43  jz      short loc_140018A4E
0x140018a45  mov     rcx, [rdi]; hWnd
0x140018a48  call    cs:__imp_DestroyWindow
0x140018a4e  mov     rbx, [rsp+38h+arg_0]
0x140018a53  add     rsp, 30h
0x140018a57  pop     rdi
0x140018a58  retn
```
