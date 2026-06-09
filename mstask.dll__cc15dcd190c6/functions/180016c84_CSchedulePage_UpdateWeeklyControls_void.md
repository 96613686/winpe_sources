# CSchedulePage::_UpdateWeeklyControls(void)

- ea: `0x180016c84`
- end: `0x180016d36`
- name: `?_UpdateWeeklyControls@CSchedulePage@@AEAAXXZ`
- size: `178`
- prototype: `void __fastcall(CSchedulePage *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x180015db8`

## callees

- `0x180016c84`

## import_xrefs

- `USER32!SendMessageW` at `0x180016cb5`
- `USER32!SendMessageW` at `0x180016cb5`
- `USER32!CheckDlgButton` at `0x180016d16`
- `USER32!CheckDlgButton` at `0x180016d16`
- `USER32!GetDlgItem` at `0x180016ca0`
- `USER32!GetDlgItem` at `0x180016ca0`
- `USER32!SendDlgItemMessageW` at `0x180016cdd`
- `USER32!SendDlgItemMessageW` at `0x180016cdd`

## pseudocode

```c
void __fastcall CSchedulePage::_UpdateWeeklyControls(HWND *this)
{
  HWND DlgItem; // rax
  __int64 i; // rbx

  DlgItem = GetDlgItem(this[14], 1690);
  SendMessageW(DlgItem, 0x14Eu, 1u, 0);
  SendDlgItemMessageW(this[14], 1714, 0x467u, 0, *((unsigned __int16 *)this[91] + 30));
  for ( i = 0; i != 7; ++i )
    CheckDlgButton(
      this[14],
      *(&g_aDayData + 3 * i),
      (*((unsigned __int16 *)this[91] + 31) & *(&g_aDayData + 3 * i + 2)) != 0);
}

```

## disassembly

```asm
0x180016c84  mov     [rsp+arg_0], rbx
0x180016c89  mov     [rsp+arg_8], rdi
0x180016c8e  push    r14
0x180016c90  sub     rsp, 30h
0x180016c94  mov     rdi, rcx
0x180016c97  mov     edx, 69Ah; nIDDlgItem
0x180016c9c  mov     rcx, [rcx+70h]; hDlg
0x180016ca0  call    cs:__imp_GetDlgItem
0x180016ca6  xor     r9d, r9d; lParam
0x180016ca9  mov     edx, 14Eh; Msg
0x180016cae  mov     rcx, rax; hWnd
0x180016cb1  lea     r8d, [r9+1]; wParam
0x180016cb5  call    cs:__imp_SendMessageW
0x180016cbb  mov     rax, [rdi+2D8h]
0x180016cc2  xor     r9d, r9d; wParam
0x180016cc5  mov     rcx, [rdi+70h]; hDlg
0x180016cc9  mov     r8d, 467h; Msg
0x180016ccf  movzx   edx, word ptr [rax+3Ch]
0x180016cd3  mov     [rsp+38h+lParam], rdx; lParam
0x180016cd8  mov     edx, 6B2h; nIDDlgItem
0x180016cdd  call    cs:__imp_SendDlgItemMessageW
0x180016ce3  xor     ebx, ebx
0x180016ce5  lea     r14, ?g_aDayData@@3PAUSDayData@@A; SDayData near * g_aDayData
0x180016cec  mov     rax, [rdi+2D8h]
0x180016cf3  lea     r9, [rbx+rbx*2]
0x180016cf7  mov     edx, [r14+r9*4]; nIDButton
0x180016cfb  mov     rcx, [rdi+70h]; hDlg
0x180016cff  movzx   r8d, word ptr [rax+3Eh]
0x180016d04  test    [r14+r9*4+8], r8d
0x180016d09  jz      short loc_180016D13
0x180016d0b  mov     r8d, 1
0x180016d11  jmp     short loc_180016D16
0x180016d13  xor     r8d, r8d; uCheck
0x180016d16  call    cs:__imp_CheckDlgButton
0x180016d1c  inc     rbx
0x180016d1f  cmp     rbx, 7
0x180016d23  jnz     short loc_180016CEC
0x180016d25  mov     rbx, [rsp+38h+arg_0]
0x180016d2a  mov     rdi, [rsp+38h+arg_8]
0x180016d2f  add     rsp, 30h
0x180016d33  pop     r14
0x180016d35  retn
```
