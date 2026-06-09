# CConfigAdvancedPage::ReadOutboxConfiguration(HWND__ *)

- ea: `0x180014ef0`
- end: `0x18001500f`
- name: `?ReadOutboxConfiguration@CConfigAdvancedPage@@AEAAKPEAUHWND__@@@Z`
- size: `287`
- prototype: `unsigned int(CConfigAdvancedPage *__hidden this, HWND)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x180014920`

## callees

- `0x180015cf0`

## import_xrefs

- `USER32!GetDlgItemInt` at `0x180014f45`
- `USER32!GetDlgItemInt` at `0x180014f63`
- `USER32!GetDlgItemInt` at `0x180014f45`
- `USER32!GetDlgItemInt` at `0x180014f63`
- `USER32!IsDlgButtonChecked` at `0x180014f1f`
- `USER32!IsDlgButtonChecked` at `0x180014f1f`
- `USER32!SendDlgItemMessageW` at `0x180014f8e`
- `USER32!SendDlgItemMessageW` at `0x180014fcf`
- `USER32!SendDlgItemMessageW` at `0x180014f8e`
- `USER32!SendDlgItemMessageW` at `0x180014fcf`

## pseudocode

```c
__int64 __fastcall CConfigAdvancedPage::ReadOutboxConfiguration(CConfigAdvancedPage *this, HWND a2)
{
  LPARAM lParam[2]; // [rsp+30h] [rbp-28h] BYREF

  *(_OWORD *)lParam = 0;
  *(_DWORD *)(*((_QWORD *)this + 71) + 32LL) = IsDlgButtonChecked(a2, 4523) == 1;
  *(_DWORD *)(*((_QWORD *)this + 71) + 12LL) = GetDlgItemInt(a2, 4526, 0, 0);
  *(_DWORD *)(*((_QWORD *)this + 71) + 16LL) = GetDlgItemInt(a2, 4529, 0, 0);
  SendDlgItemMessageW(a2, 4534, 0x1001u, 0, (LPARAM)lParam);
  *(_DWORD *)(*((_QWORD *)this + 71) + 20LL) = lParam[1];
  SendDlgItemMessageW(a2, 4535, 0x1001u, 0, (LPARAM)lParam);
  *(_DWORD *)(*((_QWORD *)this + 71) + 24LL) = lParam[1];
  return 0;
}

```

## disassembly

```asm
0x180014ef0  mov     [rsp+arg_10], rbx
0x180014ef5  push    rdi
0x180014ef6  sub     rsp, 50h
0x180014efa  mov     rax, cs:__security_cookie
0x180014f01  xor     rax, rsp
0x180014f04  mov     [rsp+58h+var_18], rax
0x180014f09  mov     rbx, rdx
0x180014f0c  mov     rdi, rcx
0x180014f0f  xorps   xmm0, xmm0
0x180014f12  mov     rcx, rbx; hDlg
0x180014f15  mov     edx, 11ABh; nIDButton
0x180014f1a  movups  xmmword ptr [rsp+58h+var_28], xmm0
0x180014f1f  call    cs:__imp_IsDlgButtonChecked
0x180014f25  xor     edx, edx
0x180014f27  mov     rcx, rbx; hDlg
0x180014f2a  cmp     eax, 1
0x180014f2d  mov     rax, [rdi+238h]
0x180014f34  setz    dl
0x180014f37  xor     r9d, r9d; bSigned
0x180014f3a  xor     r8d, r8d; lpTranslated
0x180014f3d  mov     [rax+20h], edx
0x180014f40  mov     edx, 11AEh; nIDDlgItem
0x180014f45  call    cs:__imp_GetDlgItemInt
0x180014f4b  mov     rcx, [rdi+238h]
0x180014f52  xor     r9d, r9d; bSigned
0x180014f55  xor     r8d, r8d; lpTranslated
0x180014f58  mov     edx, 11B1h; nIDDlgItem
0x180014f5d  mov     [rcx+0Ch], eax
0x180014f60  mov     rcx, rbx; hDlg
0x180014f63  call    cs:__imp_GetDlgItemInt
0x180014f69  mov     rcx, [rdi+238h]
0x180014f70  xor     r9d, r9d; wParam
0x180014f73  mov     edx, 11B6h; nIDDlgItem
0x180014f78  mov     r8d, 1001h; Msg
0x180014f7e  mov     [rcx+10h], eax
0x180014f81  lea     rax, [rsp+58h+var_28]
0x180014f86  mov     rcx, rbx; hDlg
0x180014f89  mov     [rsp+58h+lParam], rax; lParam
0x180014f8e  call    cs:__imp_SendDlgItemMessageW
0x180014f94  movzx   eax, word ptr [rsp+58h+var_28+8]
0x180014f99  xor     r9d, r9d; wParam
0x180014f9c  mov     rdx, [rdi+238h]
0x180014fa3  mov     r8d, 1001h; Msg
0x180014fa9  mov     rcx, rbx; hDlg
0x180014fac  mov     [rdx+14h], ax
0x180014fb0  mov     rdx, [rdi+238h]
0x180014fb7  movzx   eax, word ptr [rsp+58h+var_28+0Ah]
0x180014fbc  mov     [rdx+16h], ax
0x180014fc0  lea     rax, [rsp+58h+var_28]
0x180014fc5  mov     edx, 11B7h; nIDDlgItem
0x180014fca  mov     [rsp+58h+lParam], rax; lParam
0x180014fcf  call    cs:__imp_SendDlgItemMessageW
0x180014fd5  movzx   eax, word ptr [rsp+58h+var_28+8]
0x180014fda  mov     rcx, [rdi+238h]
0x180014fe1  mov     [rcx+18h], ax
0x180014fe5  movzx   eax, word ptr [rsp+58h+var_28+0Ah]
0x180014fea  mov     rcx, [rdi+238h]
0x180014ff1  mov     [rcx+1Ah], ax
0x180014ff5  xor     eax, eax
0x180014ff7  mov     rcx, [rsp+58h+var_18]
0x180014ffc  xor     rcx, rsp; StackCookie
0x180014fff  call    __security_check_cookie
0x180015004  mov     rbx, [rsp+58h+arg_10]
0x180015009  add     rsp, 50h
0x18001500d  pop     rdi
0x18001500e  retn
```
