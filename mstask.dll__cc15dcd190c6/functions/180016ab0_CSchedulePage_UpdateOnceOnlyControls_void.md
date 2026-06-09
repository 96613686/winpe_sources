# CSchedulePage::_UpdateOnceOnlyControls(void)

- ea: `0x180016ab0`
- end: `0x180016b69`
- name: `?_UpdateOnceOnlyControls@CSchedulePage@@AEAAXXZ`
- size: `185`
- prototype: `void __fastcall(CSchedulePage *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x180015db8`

## callees

- `0x180016ab0`
- `0x18001aac0`

## import_xrefs

- `USER32!SendMessageW` at `0x180016ae6`
- `USER32!SendMessageW` at `0x180016b50`
- `USER32!SendMessageW` at `0x180016ae6`
- `USER32!SendMessageW` at `0x180016b50`
- `USER32!GetDlgItem` at `0x180016ad1`
- `USER32!GetDlgItem` at `0x180016b35`
- `USER32!GetDlgItem` at `0x180016ad1`
- `USER32!GetDlgItem` at `0x180016b35`

## pseudocode

```c
void __fastcall CSchedulePage::_UpdateOnceOnlyControls(HWND *this)
{
  HWND DlgItem; // rax
  LPARAM *v3; // rax
  __int64 v4; // rcx
  HWND v5; // rcx
  __int16 v6; // ax
  HWND v7; // rcx
  HWND v8; // rax
  LPARAM lParam[2]; // [rsp+20h] [rbp-28h] BYREF

  DlgItem = GetDlgItem(this[14], 1690);
  SendMessageW(DlgItem, 0x14Eu, 3u, 0);
  v3 = lParam;
  *(_OWORD *)lParam = 0;
  v4 = 16;
  do
  {
    *(_BYTE *)v3 = 0;
    v3 = (LPARAM *)((char *)v3 + 1);
    --v4;
  }
  while ( v4 );
  v5 = this[91];
  LODWORD(lParam[0]) = v5[7];
  v6 = *((_WORD *)v5 + 16);
  v7 = this[14];
  HIWORD(lParam[0]) = v6;
  v8 = GetDlgItem(v7, 1763);
  if ( v8 )
    SendMessageW(v8, 0x1002u, 0, (LPARAM)lParam);
}

```

## disassembly

```asm
0x180016ab0  push    rbx
0x180016ab2  sub     rsp, 40h
0x180016ab6  mov     rax, cs:__security_cookie
0x180016abd  xor     rax, rsp
0x180016ac0  mov     [rsp+48h+var_18], rax
0x180016ac5  mov     rbx, rcx
0x180016ac8  mov     edx, 69Ah; nIDDlgItem
0x180016acd  mov     rcx, [rcx+70h]; hDlg
0x180016ad1  call    cs:__imp_GetDlgItem
0x180016ad7  xor     r9d, r9d; lParam
0x180016ada  mov     edx, 14Eh; Msg
0x180016adf  mov     rcx, rax; hWnd
0x180016ae2  lea     r8d, [r9+3]; wParam
0x180016ae6  call    cs:__imp_SendMessageW
0x180016aec  xorps   xmm0, xmm0
0x180016aef  lea     rax, [rsp+48h+lParam]
0x180016af4  movups  xmmword ptr [rsp+48h+lParam], xmm0
0x180016af9  mov     ecx, 10h
0x180016afe  mov     byte ptr [rax], 0
0x180016b01  inc     rax
0x180016b04  sub     rcx, 1
0x180016b08  jnz     short loc_180016AFE
0x180016b0a  mov     rcx, [rbx+2D8h]
0x180016b11  mov     edx, 6E3h; nIDDlgItem
0x180016b16  movzx   eax, word ptr [rcx+1Ch]
0x180016b1a  mov     word ptr [rsp+48h+lParam], ax
0x180016b1f  movzx   eax, word ptr [rcx+1Eh]
0x180016b23  mov     word ptr [rsp+48h+lParam+2], ax
0x180016b28  movzx   eax, word ptr [rcx+20h]
0x180016b2c  mov     rcx, [rbx+70h]; hDlg
0x180016b30  mov     word ptr [rsp+48h+lParam+6], ax
0x180016b35  call    cs:__imp_GetDlgItem
0x180016b3b  test    rax, rax
0x180016b3e  jz      short loc_180016B56
0x180016b40  lea     r9, [rsp+48h+lParam]; lParam
0x180016b45  xor     r8d, r8d; wParam
0x180016b48  mov     edx, 1002h; Msg
0x180016b4d  mov     rcx, rax; hWnd
0x180016b50  call    cs:__imp_SendMessageW
0x180016b56  mov     rcx, [rsp+48h+var_18]
0x180016b5b  xor     rcx, rsp; StackCookie
0x180016b5e  call    __security_check_cookie
0x180016b63  add     rsp, 40h
0x180016b67  pop     rbx
0x180016b68  retn
```
