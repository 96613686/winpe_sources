# _UpdateTextAndScroll(HWND__ * const,short,ushort,ushort)

- ea: `0x18000eb4c`
- end: `0x18000eba4`
- name: `?_UpdateTextAndScroll@@YAXQEAUHWND__@@FGG@Z`
- size: `88`
- prototype: `void __fastcall(HWND hDlg, __int16, unsigned __int16, unsigned __int16)`
- caller_count: `1`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x18000dc18`

## callees

- `0x180008300`

## import_xrefs

- `ext-ms-win-ntuser-dialogbox-l1-1-0!SendDlgItemMessageW` at `0x18000eb87`
- `ext-ms-win-ntuser-dialogbox-l1-1-0!SendDlgItemMessageW` at `0x18000eb87`

## pseudocode

```c
void __fastcall _UpdateTextAndScroll(HWND hDlg, unsigned __int16 a2, unsigned __int16 a3, unsigned __int16 a4)
{
  LPARAM lParam; // rbx
  int v6; // edi

  lParam = a2;
  v6 = a4;
  UpdateItem(hDlg, a3, (__int16)a2);
  SendDlgItemMessageW(hDlg, v6, 0x467u, 0, lParam);
}

```

## disassembly

```asm
0x18000eb4c  mov     [rsp+arg_0], rbx
0x18000eb51  mov     [rsp+arg_8], rsi
0x18000eb56  push    rdi
0x18000eb57  sub     rsp, 30h
0x18000eb5b  movzx   eax, r8w
0x18000eb5f  mov     rsi, rcx
0x18000eb62  movzx   ebx, dx
0x18000eb65  mov     edx, eax; nIDDlgItem
0x18000eb67  movsx   r8d, bx; unsigned int
0x18000eb6b  movzx   edi, r9w
0x18000eb6f  call    ?UpdateItem@@YAXPEAUHWND__@@II@Z; UpdateItem(HWND__ *,uint,uint)
0x18000eb74  mov     edx, edi; nIDDlgItem
0x18000eb76  mov     [rsp+38h+lParam], rbx; lParam
0x18000eb7b  xor     r9d, r9d; wParam
0x18000eb7e  mov     r8d, 467h; Msg
0x18000eb84  mov     rcx, rsi; hDlg
0x18000eb87  call    cs:__imp_SendDlgItemMessageW
0x18000eb8e  nop     dword ptr [rax+rax+00h]
0x18000eb93  mov     rbx, [rsp+38h+arg_0]
0x18000eb98  mov     rsi, [rsp+38h+arg_8]
0x18000eb9d  add     rsp, 30h
0x18000eba1  pop     rdi
0x18000eba2  retn
```
