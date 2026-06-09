# DevicesPage::UpdateProfileListViewEnabledState(int)

- ea: `0x18000e6b0`
- end: `0x18000e7a4`
- name: `?UpdateProfileListViewEnabledState@DevicesPage@@AEAAJH@Z`
- size: `244`
- prototype: `__int64 __fastcall(DevicesPage *this, BOOL)`
- caller_count: `2`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x18000d67c`
- `0x18000e144`

## callees

- `0x18000e6b0`
- `0x18001327c`

## import_xrefs

- `USER32!GetDlgItem` at `0x18000e6f8`
- `USER32!GetDlgItem` at `0x18000e713`
- `USER32!GetDlgItem` at `0x18000e743`
- `USER32!GetDlgItem` at `0x18000e769`
- `USER32!GetDlgItem` at `0x18000e783`
- `USER32!GetDlgItem` at `0x18000e6f8`
- `USER32!GetDlgItem` at `0x18000e713`
- `USER32!GetDlgItem` at `0x18000e743`
- `USER32!GetDlgItem` at `0x18000e769`
- `USER32!GetDlgItem` at `0x18000e783`
- `USER32!EnableWindow` at `0x18000e704`
- `USER32!EnableWindow` at `0x18000e71f`
- `USER32!EnableWindow` at `0x18000e74e`
- `USER32!EnableWindow` at `0x18000e774`
- `USER32!EnableWindow` at `0x18000e78f`
- `USER32!EnableWindow` at `0x18000e704`
- `USER32!EnableWindow` at `0x18000e71f`
- `USER32!EnableWindow` at `0x18000e74e`
- `USER32!EnableWindow` at `0x18000e774`
- `USER32!EnableWindow` at `0x18000e78f`

## pseudocode

```c
__int64 __fastcall DevicesPage::UpdateProfileListViewEnabledState(DevicesPage *this, BOOL a2)
{
  __int64 result; // rax
  unsigned int v5; // edi
  BOOL v6; // r15d
  HWND DlgItem; // rax
  HWND v8; // rax
  BOOL v9; // ebp
  BOOL v10; // esi
  HWND v11; // rax
  HWND v12; // rax
  HWND v13; // rax
  int v14; // [rsp+60h] [rbp+8h] BYREF

  v14 = 0;
  result = ListView::GetSelectedItemIndex(*((HWND **)this + 10), (unsigned int *)&v14);
  v5 = result;
  if ( (int)result >= 0 )
  {
    v6 = v14 != -1;
    DlgItem = GetDlgItem(*((HWND *)this + 1), 1108);
    EnableWindow(DlgItem, a2);
    v8 = GetDlgItem(*((HWND *)this + 1), 1111);
    EnableWindow(v8, a2);
    v9 = 1;
    v10 = a2 && v6;
    v11 = GetDlgItem(*((HWND *)this + 1), 1112);
    EnableWindow(v11, v10);
    if ( !a2 || !v6 )
      v9 = 0;
    v12 = GetDlgItem(*((HWND *)this + 1), 1113);
    EnableWindow(v12, v9);
    v13 = GetDlgItem(*((HWND *)this + 1), 1117);
    EnableWindow(v13, a2);
    return v5;
  }
  return result;
}

```

## disassembly

```asm
0x18000e6b0  push    rbx
0x18000e6b2  push    rbp
0x18000e6b3  push    rsi
0x18000e6b4  push    rdi
0x18000e6b5  push    r14
0x18000e6b7  push    r15
0x18000e6b9  sub     rsp, 28h
0x18000e6bd  mov     r14d, edx
0x18000e6c0  mov     [rsp+58h+arg_0], 0
0x18000e6c8  mov     rbx, rcx
0x18000e6cb  lea     rdx, [rsp+58h+arg_0]; int *
0x18000e6d0  mov     rcx, [rcx+50h]; this
0x18000e6d4  call    ?GetSelectedItemIndex@ListView@@QEBAJPEAH@Z; ListView::GetSelectedItemIndex(int *)
0x18000e6d9  mov     edi, eax
0x18000e6db  test    eax, eax
0x18000e6dd  js      loc_18000E797
0x18000e6e3  mov     rcx, [rbx+8]; hDlg
0x18000e6e7  xor     r15d, r15d
0x18000e6ea  cmp     [rsp+58h+arg_0], 0FFFFFFFFh
0x18000e6ef  mov     edx, 454h; nIDDlgItem
0x18000e6f4  setnz   r15b
0x18000e6f8  call    cs:__imp_GetDlgItem
0x18000e6fe  mov     rcx, rax; hWnd
0x18000e701  mov     edx, r14d; bEnable
0x18000e704  call    cs:__imp_EnableWindow
0x18000e70a  mov     rcx, [rbx+8]; hDlg
0x18000e70e  mov     edx, 457h; nIDDlgItem
0x18000e713  call    cs:__imp_GetDlgItem
0x18000e719  mov     rcx, rax; hWnd
0x18000e71c  mov     edx, r14d; bEnable
0x18000e71f  call    cs:__imp_EnableWindow
0x18000e725  mov     ebp, 1
0x18000e72a  test    r14d, r14d
0x18000e72d  jz      short loc_18000E738
0x18000e72f  test    r15d, r15d
0x18000e732  jz      short loc_18000E738
0x18000e734  mov     esi, ebp
0x18000e736  jmp     short loc_18000E73A
0x18000e738  xor     esi, esi
0x18000e73a  mov     rcx, [rbx+8]; hDlg
0x18000e73e  mov     edx, 458h; nIDDlgItem
0x18000e743  call    cs:__imp_GetDlgItem
0x18000e749  mov     rcx, rax; hWnd
0x18000e74c  mov     edx, esi; bEnable
0x18000e74e  call    cs:__imp_EnableWindow
0x18000e754  test    r14d, r14d
0x18000e757  jz      short loc_18000E75E
0x18000e759  test    r15d, r15d
0x18000e75c  jnz     short loc_18000E760
0x18000e75e  xor     ebp, ebp
0x18000e760  mov     rcx, [rbx+8]; hDlg
0x18000e764  mov     edx, 459h; nIDDlgItem
0x18000e769  call    cs:__imp_GetDlgItem
0x18000e76f  mov     rcx, rax; hWnd
0x18000e772  mov     edx, ebp; bEnable
0x18000e774  call    cs:__imp_EnableWindow
0x18000e77a  mov     rcx, [rbx+8]; hDlg
0x18000e77e  mov     edx, 45Dh; nIDDlgItem
0x18000e783  call    cs:__imp_GetDlgItem
0x18000e789  mov     rcx, rax; hWnd
0x18000e78c  mov     edx, r14d; bEnable
0x18000e78f  call    cs:__imp_EnableWindow
0x18000e795  mov     eax, edi
0x18000e797  add     rsp, 28h
0x18000e79b  pop     r15
0x18000e79d  pop     r14
0x18000e79f  pop     rdi
0x18000e7a0  pop     rsi
0x18000e7a1  pop     rbp
0x18000e7a2  pop     rbx
0x18000e7a3  retn
```
