# CSchedulePage::_UpdateMonthlyControls(void)

- ea: `0x1800168a4`
- end: `0x180016aaa`
- name: `?_UpdateMonthlyControls@CSchedulePage@@AEAAXXZ`
- size: `518`
- prototype: `void __fastcall(CSchedulePage *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, installer_update`

## callers

- `0x180015db8`

## callees

- `0x1800137bc`
- `0x180013f4c`
- `0x1800168a4`

## import_xrefs

- `USER32!SendMessageW` at `0x1800168cf`
- `USER32!SendMessageW` at `0x1800169dd`
- `USER32!SendMessageW` at `0x180016a45`
- `USER32!SendMessageW` at `0x1800168cf`
- `USER32!SendMessageW` at `0x1800169dd`
- `USER32!SendMessageW` at `0x180016a45`
- `USER32!EnableWindow` at `0x180016946`
- `USER32!EnableWindow` at `0x180016968`
- `USER32!EnableWindow` at `0x180016987`
- `USER32!EnableWindow` at `0x1800169f4`
- `USER32!EnableWindow` at `0x180016a5c`
- `USER32!EnableWindow` at `0x180016a7b`
- `USER32!EnableWindow` at `0x180016a9a`
- `USER32!EnableWindow` at `0x180016946`
- `USER32!EnableWindow` at `0x180016968`
- `USER32!EnableWindow` at `0x180016987`
- `USER32!EnableWindow` at `0x1800169f4`
- `USER32!EnableWindow` at `0x180016a5c`
- `USER32!EnableWindow` at `0x180016a7b`
- `USER32!EnableWindow` at `0x180016a9a`
- `USER32!GetDlgItem` at `0x1800168ba`
- `USER32!GetDlgItem` at `0x180016933`
- `USER32!GetDlgItem` at `0x180016955`
- `USER32!GetDlgItem` at `0x180016977`
- `USER32!GetDlgItem` at `0x1800169c1`
- `USER32!GetDlgItem` at `0x180016a29`
- `USER32!GetDlgItem` at `0x180016a6b`
- `USER32!GetDlgItem` at `0x180016a8a`
- `USER32!GetDlgItem` at `0x1800168ba`
- `USER32!GetDlgItem` at `0x180016933`
- `USER32!GetDlgItem` at `0x180016955`
- `USER32!GetDlgItem` at `0x180016977`
- `USER32!GetDlgItem` at `0x1800169c1`
- `USER32!GetDlgItem` at `0x180016a29`
- `USER32!GetDlgItem` at `0x180016a6b`
- `USER32!GetDlgItem` at `0x180016a8a`
- `USER32!SendDlgItemMessageW` at `0x18001691b`
- `USER32!SendDlgItemMessageW` at `0x18001691b`

## pseudocode

```c
void __fastcall CSchedulePage::_UpdateMonthlyControls(HWND *this)
{
  HWND DlgItem; // rax
  CSchedulePage *v3; // rcx
  HWND v4; // rax
  unsigned __int16 DayFromRgfDays; // ax
  HWND v6; // rax
  HWND v7; // rax
  HWND v8; // rax
  int v9; // edx
  unsigned int i; // esi
  HWND v11; // rax
  HWND v12; // rbp
  unsigned int j; // esi
  HWND v14; // rax
  HWND v15; // rbp
  HWND v16; // rax
  HWND v17; // rax

  DlgItem = GetDlgItem(this[14], 1690);
  SendMessageW(DlgItem, 0x14Eu, 2u, 0);
  CSchedulePage::_CheckMonthlyRadio((CSchedulePage *)this, *((enum _TASK_TRIGGER_TYPE *)this[91] + 14));
  v4 = this[91];
  if ( *((_DWORD *)v4 + 14) == 3 )
  {
    DayFromRgfDays = CSchedulePage::_GetDayFromRgfDays(v3, *((_DWORD *)v4 + 15));
    SendDlgItemMessageW(this[14], 1734, 0x467u, 0, DayFromRgfDays);
    if ( !*((_DWORD *)this + 192) )
    {
      v6 = GetDlgItem(this[14], 1734);
      if ( v6 )
        EnableWindow(v6, 1);
      v7 = GetDlgItem(this[14], 1733);
      if ( v7 )
        EnableWindow(v7, 1);
    }
    v8 = GetDlgItem(this[14], 1737);
    if ( v8 )
      EnableWindow(v8, 0);
    v9 = 1738;
  }
  else
  {
    for ( i = 0; i < 5; ++i )
    {
      if ( dword_180023474[2 * i] == *((unsigned __int16 *)v4 + 30) )
        break;
    }
    v11 = GetDlgItem(this[14], 1737);
    v12 = v11;
    if ( v11 )
    {
      SendMessageW(v11, 0x14Eu, (int)i, 0);
      if ( !*((_DWORD *)this + 192) )
        EnableWindow(v12, 1);
    }
    for ( j = 0; j < 7; ++j )
    {
      if ( (*((unsigned __int16 *)this[91] + 31) & dword_180023418[3 * j]) != 0 )
        break;
    }
    v14 = GetDlgItem(this[14], 1738);
    v15 = v14;
    if ( v14 )
    {
      SendMessageW(v14, 0x14Eu, (int)j, 0);
      if ( !*((_DWORD *)this + 192) )
        EnableWindow(v15, 1);
    }
    v16 = GetDlgItem(this[14], 1733);
    if ( v16 )
      EnableWindow(v16, 0);
    v9 = 1734;
  }
  v17 = GetDlgItem(this[14], v9);
  if ( v17 )
    EnableWindow(v17, 0);
}

```

## disassembly

```asm
0x1800168a4  push    rbx
0x1800168a6  push    rbp
0x1800168a7  push    rsi
0x1800168a8  push    r14
0x1800168aa  sub     rsp, 38h
0x1800168ae  mov     rbx, rcx
0x1800168b1  mov     edx, 69Ah; nIDDlgItem
0x1800168b6  mov     rcx, [rcx+70h]; hDlg
0x1800168ba  call    cs:__imp_GetDlgItem
0x1800168c0  xor     r9d, r9d; lParam
0x1800168c3  mov     edx, 14Eh; Msg
0x1800168c8  mov     rcx, rax; hWnd
0x1800168cb  lea     r8d, [r9+2]; wParam
0x1800168cf  call    cs:__imp_SendMessageW
0x1800168d5  mov     rdx, [rbx+2D8h]
0x1800168dc  mov     rcx, rbx; this
0x1800168df  mov     edx, [rdx+38h]; enum _TASK_TRIGGER_TYPE
0x1800168e2  call    ?_CheckMonthlyRadio@CSchedulePage@@AEAAXW4_TASK_TRIGGER_TYPE@@@Z; CSchedulePage::_CheckMonthlyRadio(_TASK_TRIGGER_TYPE)
0x1800168e7  mov     rax, [rbx+2D8h]
0x1800168ee  cmp     dword ptr [rax+38h], 3
0x1800168f2  jnz     loc_180016997
0x1800168f8  mov     edx, [rax+3Ch]; unsigned int
0x1800168fb  call    ?_GetDayFromRgfDays@CSchedulePage@@AEAAGK@Z; CSchedulePage::_GetDayFromRgfDays(ulong)
0x180016900  mov     rcx, [rbx+70h]; hDlg
0x180016904  xor     r9d, r9d; wParam
0x180016907  movzx   r10d, ax
0x18001690b  mov     edx, 6C6h; nIDDlgItem
0x180016910  mov     r8d, 467h; Msg
0x180016916  mov     [rsp+58h+lParam], r10; lParam
0x18001691b  call    cs:__imp_SendDlgItemMessageW
0x180016921  cmp     dword ptr [rbx+300h], 0
0x180016928  jnz     short loc_18001696E
0x18001692a  mov     rcx, [rbx+70h]; hDlg
0x18001692e  mov     edx, 6C6h; nIDDlgItem
0x180016933  call    cs:__imp_GetDlgItem
0x180016939  test    rax, rax
0x18001693c  jz      short loc_18001694C
0x18001693e  mov     edx, 1; bEnable
0x180016943  mov     rcx, rax; hWnd
0x180016946  call    cs:__imp_EnableWindow
0x18001694c  mov     rcx, [rbx+70h]; hDlg
0x180016950  mov     edx, 6C5h; nIDDlgItem
0x180016955  call    cs:__imp_GetDlgItem
0x18001695b  test    rax, rax
0x18001695e  jz      short loc_18001696E
0x180016960  mov     edx, 1; bEnable
0x180016965  mov     rcx, rax; hWnd
0x180016968  call    cs:__imp_EnableWindow
0x18001696e  mov     rcx, [rbx+70h]; hDlg
0x180016972  mov     edx, 6C9h; nIDDlgItem
0x180016977  call    cs:__imp_GetDlgItem
0x18001697d  test    rax, rax
0x180016980  jz      short loc_18001698D
0x180016982  xor     edx, edx; bEnable
0x180016984  mov     rcx, rax; hWnd
0x180016987  call    cs:__imp_EnableWindow
0x18001698d  mov     edx, 6CAh
0x180016992  jmp     loc_180016A86
0x180016997  movzx   ecx, word ptr [rax+3Ch]
0x18001699b  lea     r14, __ImageBase
0x1800169a2  xor     esi, esi
0x1800169a4  movsxd  rax, esi
0x1800169a7  cmp     rva dword_180023474[r14+rax*8], ecx
0x1800169af  jz      short loc_1800169B8
0x1800169b1  inc     esi
0x1800169b3  cmp     esi, 5
0x1800169b6  jb      short loc_1800169A4
0x1800169b8  mov     rcx, [rbx+70h]; hDlg
0x1800169bc  mov     edx, 6C9h; nIDDlgItem
0x1800169c1  call    cs:__imp_GetDlgItem
0x1800169c7  mov     rbp, rax
0x1800169ca  test    rax, rax
0x1800169cd  jz      short loc_1800169FA
0x1800169cf  movsxd  r8, esi; wParam
0x1800169d2  xor     r9d, r9d; lParam
0x1800169d5  mov     edx, 14Eh; Msg
0x1800169da  mov     rcx, rax; hWnd
0x1800169dd  call    cs:__imp_SendMessageW
0x1800169e3  cmp     dword ptr [rbx+300h], 0
0x1800169ea  jnz     short loc_1800169FA
0x1800169ec  mov     edx, 1; bEnable
0x1800169f1  mov     rcx, rbp; hWnd
0x1800169f4  call    cs:__imp_EnableWindow
0x1800169fa  mov     rax, [rbx+2D8h]
0x180016a01  xor     esi, esi
0x180016a03  movzx   r8d, word ptr [rax+3Eh]
0x180016a08  movsxd  rax, esi
0x180016a0b  lea     rcx, [rax+rax*2]
0x180016a0f  test    rva dword_180023418[r14+rcx*4], r8d
0x180016a17  jnz     short loc_180016A20
0x180016a19  inc     esi
0x180016a1b  cmp     esi, 7
0x180016a1e  jb      short loc_180016A08
0x180016a20  mov     rcx, [rbx+70h]; hDlg
0x180016a24  mov     edx, 6CAh; nIDDlgItem
0x180016a29  call    cs:__imp_GetDlgItem
0x180016a2f  mov     rbp, rax
0x180016a32  test    rax, rax
0x180016a35  jz      short loc_180016A62
0x180016a37  movsxd  r8, esi; wParam
0x180016a3a  xor     r9d, r9d; lParam
0x180016a3d  mov     edx, 14Eh; Msg
0x180016a42  mov     rcx, rax; hWnd
0x180016a45  call    cs:__imp_SendMessageW
0x180016a4b  cmp     dword ptr [rbx+300h], 0
0x180016a52  jnz     short loc_180016A62
0x180016a54  mov     edx, 1; bEnable
0x180016a59  mov     rcx, rbp; hWnd
0x180016a5c  call    cs:__imp_EnableWindow
0x180016a62  mov     rcx, [rbx+70h]; hDlg
0x180016a66  mov     edx, 6C5h; nIDDlgItem
0x180016a6b  call    cs:__imp_GetDlgItem
0x180016a71  test    rax, rax
0x180016a74  jz      short loc_180016A81
0x180016a76  xor     edx, edx; bEnable
0x180016a78  mov     rcx, rax; hWnd
0x180016a7b  call    cs:__imp_EnableWindow
0x180016a81  mov     edx, 6C6h; nIDDlgItem
0x180016a86  mov     rcx, [rbx+70h]; hDlg
0x180016a8a  call    cs:__imp_GetDlgItem
0x180016a90  test    rax, rax
0x180016a93  jz      short loc_180016AA0
0x180016a95  xor     edx, edx; bEnable
0x180016a97  mov     rcx, rax; hWnd
0x180016a9a  call    cs:__imp_EnableWindow
0x180016aa0  add     rsp, 38h
0x180016aa4  pop     r14
0x180016aa6  pop     rsi
0x180016aa7  pop     rbp
0x180016aa8  pop     rbx
0x180016aa9  retn
```
