# CSettingsPage::_ReadIdleSettings(void)

- ea: `0x180017d20`
- end: `0x180017dec`
- name: `?_ReadIdleSettings@CSettingsPage@@AEAAXXZ`
- size: `204`
- prototype: `void __fastcall(CSettingsPage *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180017130`
- `0x180017ba0`

## callees

- `0x180017d20`
- `0x18001b010`

## import_xrefs

- `USER32!SendDlgItemMessageW` at `0x180017d5f`
- `USER32!SendDlgItemMessageW` at `0x180017d8b`
- `USER32!SendDlgItemMessageW` at `0x180017d5f`
- `USER32!SendDlgItemMessageW` at `0x180017d8b`
- `USER32!IsDlgButtonChecked` at `0x180017d35`
- `USER32!IsDlgButtonChecked` at `0x180017d35`

## pseudocode

```c
void __fastcall CSettingsPage::_ReadIdleSettings(HWND *this)
{
  int v2; // eax
  unsigned __int16 v3; // si
  int v4; // eax
  unsigned __int16 v5; // di

  if ( IsDlgButtonChecked(this[14], 1671) == 1 )
  {
    v2 = SendDlgItemMessageW(this[14], 1684, 0x468u, 0, 0);
    if ( HIWORD(v2) )
      v3 = 10;
    else
      v3 = v2;
    v4 = SendDlgItemMessageW(this[14], 1698, 0x468u, 0, 0);
    if ( HIWORD(v4) )
      v5 = 60;
    else
      v5 = v4;
    if ( (*((_WORD *)this + 340) != v3 || *((_WORD *)this + 341) != v5)
      && (*(int (__fastcall **)(HWND, _QWORD, _QWORD))(*(_QWORD *)this[83] + 80LL))(this[83], v3, v5) >= 0 )
    {
      *((_WORD *)this + 340) = v3;
      *((_WORD *)this + 341) = v5;
    }
  }
}

```

## disassembly

```asm
0x180017d20  push    rbx
0x180017d22  push    rbp
0x180017d23  push    rsi
0x180017d24  push    rdi
0x180017d25  sub     rsp, 38h
0x180017d29  mov     rbx, rcx
0x180017d2c  mov     edx, 687h; nIDButton
0x180017d31  mov     rcx, [rcx+70h]; hDlg
0x180017d35  call    cs:__imp_IsDlgButtonChecked
0x180017d3b  cmp     eax, 1
0x180017d3e  jnz     loc_180017DE3
0x180017d44  mov     rcx, [rbx+70h]; hDlg
0x180017d48  mov     edi, 468h
0x180017d4d  xor     ebp, ebp
0x180017d4f  mov     r8d, edi; Msg
0x180017d52  xor     r9d, r9d; wParam
0x180017d55  mov     [rsp+58h+lParam], rbp; lParam
0x180017d5a  mov     edx, 694h; nIDDlgItem
0x180017d5f  call    cs:__imp_SendDlgItemMessageW
0x180017d65  mov     ecx, eax
0x180017d67  shr     ecx, 10h
0x180017d6a  test    cx, cx
0x180017d6d  jz      short loc_180017D74
0x180017d6f  lea     esi, [rbp+0Ah]
0x180017d72  jmp     short loc_180017D77
0x180017d74  movzx   esi, ax
0x180017d77  mov     rcx, [rbx+70h]; hDlg
0x180017d7b  xor     r9d, r9d; wParam
0x180017d7e  mov     r8d, edi; Msg
0x180017d81  mov     [rsp+58h+lParam], rbp; lParam
0x180017d86  mov     edx, 6A2h; nIDDlgItem
0x180017d8b  call    cs:__imp_SendDlgItemMessageW
0x180017d91  mov     ecx, eax
0x180017d93  shr     ecx, 10h
0x180017d96  test    cx, cx
0x180017d99  jz      short loc_180017DA2
0x180017d9b  mov     edi, 3Ch ; '<'
0x180017da0  jmp     short loc_180017DA5
0x180017da2  movzx   edi, ax
0x180017da5  cmp     [rbx+2A8h], si
0x180017dac  jnz     short loc_180017DB7
0x180017dae  cmp     [rbx+2AAh], di
0x180017db5  jz      short loc_180017DE3
0x180017db7  mov     rcx, [rbx+298h]
0x180017dbe  movzx   r8d, di
0x180017dc2  movzx   edx, si
0x180017dc5  mov     rax, [rcx]
0x180017dc8  mov     rax, [rax+50h]
0x180017dcc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017dd1  test    eax, eax
0x180017dd3  js      short loc_180017DE3
0x180017dd5  mov     [rbx+2A8h], si
0x180017ddc  mov     [rbx+2AAh], di
0x180017de3  add     rsp, 38h
0x180017de7  pop     rdi
0x180017de8  pop     rsi
0x180017de9  pop     rbp
0x180017dea  pop     rbx
0x180017deb  retn
```
