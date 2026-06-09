# UpdateItem(HWND__ *,uint,uint)

- ea: `0x180008300`
- end: `0x180008350`
- name: `?UpdateItem@@YAXPEAUHWND__@@II@Z`
- size: `80`
- prototype: `void __fastcall(HWND hDlg, unsigned int nIDDlgItem, unsigned int)`
- caller_count: `5`
- callee_count: `0`
- tags: `installer_update`

## callers

- `0x180008358`
- `0x18000bdf0`
- `0x18000cea0`
- `0x18000e644`
- `0x18000eb4c`

## import_xrefs

- `ext-ms-win-ntuser-dialogbox-l1-1-2!SetDlgItemInt` at `0x180008315`
- `ext-ms-win-ntuser-dialogbox-l1-1-2!SetDlgItemInt` at `0x180008315`
- `ext-ms-win-ntuser-dialogbox-l1-1-0!SendDlgItemMessageW` at `0x180008338`
- `ext-ms-win-ntuser-dialogbox-l1-1-0!SendDlgItemMessageW` at `0x180008338`

## pseudocode

```c
void __fastcall UpdateItem(HWND hDlg, int nIDDlgItem, UINT a3)
{
  SetDlgItemInt(hDlg, nIDDlgItem, a3, 1);
  SendDlgItemMessageW(hDlg, nIDDlgItem, 0xB1u, 0, -1);
}

```

## disassembly

```asm
0x180008300  mov     [rsp+arg_0], rbx
0x180008305  push    rdi
0x180008306  sub     rsp, 30h
0x18000830a  mov     r9d, 1; bSigned
0x180008310  mov     ebx, edx
0x180008312  mov     rdi, rcx
0x180008315  call    cs:__imp_SetDlgItemInt
0x18000831c  nop     dword ptr [rax+rax+00h]
0x180008321  xor     r9d, r9d; wParam
0x180008324  mov     [rsp+38h+lParam], 0FFFFFFFFFFFFFFFFh; lParam
0x18000832d  mov     r8d, 0B1h; Msg
0x180008333  mov     edx, ebx; nIDDlgItem
0x180008335  mov     rcx, rdi; hDlg
0x180008338  call    cs:__imp_SendDlgItemMessageW
0x18000833f  nop     dword ptr [rax+rax+00h]
0x180008344  mov     rbx, [rsp+38h+arg_0]
0x180008349  add     rsp, 30h
0x18000834d  pop     rdi
0x18000834e  retn
```
