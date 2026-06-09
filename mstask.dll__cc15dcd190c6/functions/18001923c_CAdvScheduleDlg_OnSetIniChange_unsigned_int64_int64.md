# CAdvScheduleDlg::_OnSetIniChange(unsigned __int64,__int64)

- ea: `0x18001923c`
- end: `0x1800192d8`
- name: `?_OnSetIniChange@CAdvScheduleDlg@@AEAA_J_K_J@Z`
- size: `156`
- prototype: `__int64 __fastcall(CAdvScheduleDlg *__hidden this, unsigned __int64, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, installer_update`

## callers

- `0x180018540`

## callees

- `0x1800135a4`
- `0x18001923c`

## import_xrefs

- `USER32!SendMessageW` at `0x18001926b`
- `USER32!SendMessageW` at `0x180019293`
- `USER32!SendMessageW` at `0x1800192c5`
- `USER32!SendMessageW` at `0x18001926b`
- `USER32!SendMessageW` at `0x180019293`
- `USER32!SendMessageW` at `0x1800192c5`
- `USER32!GetDlgItem` at `0x180019252`
- `USER32!GetDlgItem` at `0x18001927a`
- `USER32!GetDlgItem` at `0x1800192ab`
- `USER32!GetDlgItem` at `0x180019252`
- `USER32!GetDlgItem` at `0x18001927a`
- `USER32!GetDlgItem` at `0x1800192ab`

## pseudocode

```c
__int64 __fastcall CAdvScheduleDlg::_OnSetIniChange(CAdvScheduleDlg *this)
{
  HWND DlgItem; // rax
  HWND v3; // rax
  HWND v4; // rax

  DlgItem = GetDlgItem(*((HWND *)this + 1), 1773);
  if ( DlgItem )
    SendMessageW(DlgItem, 0x1032u, 0, 0);
  v3 = GetDlgItem(*((HWND *)this + 1), 1778);
  if ( v3 )
    SendMessageW(v3, 0x1032u, 0, 0);
  UpdateTimeFormat((unsigned __int16 *)this + 12);
  v4 = GetDlgItem(*((HWND *)this + 1), 1782);
  if ( v4 )
    SendMessageW(v4, 0x1032u, 0, (LPARAM)this + 24);
  return 0;
}

```

## disassembly

```asm
0x18001923c  mov     [rsp+arg_0], rbx
0x180019241  push    rdi
0x180019242  sub     rsp, 20h
0x180019246  mov     rbx, rcx
0x180019249  mov     edx, 6EDh; nIDDlgItem
0x18001924e  mov     rcx, [rcx+8]; hDlg
0x180019252  call    cs:__imp_GetDlgItem
0x180019258  test    rax, rax
0x18001925b  jz      short loc_180019271
0x18001925d  xor     r9d, r9d; lParam
0x180019260  xor     r8d, r8d; wParam
0x180019263  mov     edx, 1032h; Msg
0x180019268  mov     rcx, rax; hWnd
0x18001926b  call    cs:__imp_SendMessageW
0x180019271  mov     rcx, [rbx+8]; hDlg
0x180019275  mov     edx, 6F2h; nIDDlgItem
0x18001927a  call    cs:__imp_GetDlgItem
0x180019280  test    rax, rax
0x180019283  jz      short loc_180019299
0x180019285  xor     r9d, r9d; lParam
0x180019288  xor     r8d, r8d; wParam
0x18001928b  mov     edx, 1032h; Msg
0x180019290  mov     rcx, rax; hWnd
0x180019293  call    cs:__imp_SendMessageW
0x180019299  lea     rcx, [rbx+18h]; unsigned __int16 *
0x18001929d  call    ?UpdateTimeFormat@@YAXPEAGK@Z; UpdateTimeFormat(ushort *,ulong)
0x1800192a2  mov     rcx, [rbx+8]; hDlg
0x1800192a6  mov     edx, 6F6h; nIDDlgItem
0x1800192ab  call    cs:__imp_GetDlgItem
0x1800192b1  test    rax, rax
0x1800192b4  jz      short loc_1800192CB
0x1800192b6  lea     r9, [rbx+18h]; lParam
0x1800192ba  xor     r8d, r8d; wParam
0x1800192bd  mov     edx, 1032h; Msg
0x1800192c2  mov     rcx, rax; hWnd
0x1800192c5  call    cs:__imp_SendMessageW
0x1800192cb  mov     rbx, [rsp+28h+arg_0]
0x1800192d0  xor     eax, eax
0x1800192d2  add     rsp, 20h
0x1800192d6  pop     rdi
0x1800192d7  retn
```
