# CConfigAdvancedPage::InitializeRetryControls(HWND__ *)

- ea: `0x1800147f0`
- end: `0x180014917`
- name: `?InitializeRetryControls@CConfigAdvancedPage@@AEBAKPEAUHWND__@@@Z`
- size: `295`
- prototype: `unsigned int(CConfigAdvancedPage *__hidden this, HWND)`
- caller_count: `1`
- callee_count: `0`
- tags: `registry_config`

## callers

- `0x180014bc0`

## import_xrefs

- `USER32!SetDlgItemInt` at `0x18001487f`
- `USER32!SetDlgItemInt` at `0x180014904`
- `USER32!SetDlgItemInt` at `0x18001487f`
- `USER32!SetDlgItemInt` at `0x180014904`
- `USER32!SendDlgItemMessageW` at `0x18001481d`
- `USER32!SendDlgItemMessageW` at `0x18001483d`
- `USER32!SendDlgItemMessageW` at `0x180014863`
- `USER32!SendDlgItemMessageW` at `0x1800148a2`
- `USER32!SendDlgItemMessageW` at `0x1800148c2`
- `USER32!SendDlgItemMessageW` at `0x1800148e8`
- `USER32!SendDlgItemMessageW` at `0x18001481d`
- `USER32!SendDlgItemMessageW` at `0x18001483d`
- `USER32!SendDlgItemMessageW` at `0x180014863`
- `USER32!SendDlgItemMessageW` at `0x1800148a2`
- `USER32!SendDlgItemMessageW` at `0x1800148c2`
- `USER32!SendDlgItemMessageW` at `0x1800148e8`

## pseudocode

```c
__int64 __fastcall CConfigAdvancedPage::InitializeRetryControls(CConfigAdvancedPage *this, HWND a2)
{
  SendDlgItemMessageW(a2, 4526, 0xC5u, 2u, 0);
  SendDlgItemMessageW(a2, 4527, 0x46Fu, 0, 99);
  SendDlgItemMessageW(a2, 4527, 0x471u, 0, *(unsigned int *)(*((_QWORD *)this + 71) + 12LL));
  SetDlgItemInt(a2, 4526, *(_DWORD *)(*((_QWORD *)this + 71) + 12LL), 0);
  SendDlgItemMessageW(a2, 4529, 0xC5u, 3u, 0);
  SendDlgItemMessageW(a2, 4530, 0x46Fu, 0, 999);
  SendDlgItemMessageW(a2, 4530, 0x471u, 0, *(unsigned int *)(*((_QWORD *)this + 71) + 16LL));
  SetDlgItemInt(a2, 4529, *(_DWORD *)(*((_QWORD *)this + 71) + 16LL), 0);
  return 0;
}

```

## disassembly

```asm
0x1800147f0  mov     [rsp+arg_0], rbx
0x1800147f5  push    rdi
0x1800147f6  sub     rsp, 30h
0x1800147fa  mov     rdi, rdx
0x1800147fd  mov     [rsp+38h+lParam], 0; lParam
0x180014806  mov     rbx, rcx
0x180014809  mov     edx, 11AEh; nIDDlgItem
0x18001480e  mov     rcx, rdi; hDlg
0x180014811  mov     r9d, 2; wParam
0x180014817  mov     r8d, 0C5h; Msg
0x18001481d  call    cs:__imp_SendDlgItemMessageW
0x180014823  xor     r9d, r9d; wParam
0x180014826  mov     [rsp+38h+lParam], 63h ; 'c'; lParam
0x18001482f  mov     edx, 11AFh; nIDDlgItem
0x180014834  mov     r8d, 46Fh; Msg
0x18001483a  mov     rcx, rdi; hDlg
0x18001483d  call    cs:__imp_SendDlgItemMessageW
0x180014843  mov     rax, [rbx+238h]
0x18001484a  xor     r9d, r9d; wParam
0x18001484d  mov     edx, 11AFh; nIDDlgItem
0x180014852  mov     r8d, 471h; Msg
0x180014858  mov     ecx, [rax+0Ch]
0x18001485b  mov     [rsp+38h+lParam], rcx; lParam
0x180014860  mov     rcx, rdi; hDlg
0x180014863  call    cs:__imp_SendDlgItemMessageW
0x180014869  mov     r8, [rbx+238h]
0x180014870  xor     r9d, r9d; bSigned
0x180014873  mov     edx, 11AEh; nIDDlgItem
0x180014878  mov     rcx, rdi; hDlg
0x18001487b  mov     r8d, [r8+0Ch]; uValue
0x18001487f  call    cs:__imp_SetDlgItemInt
0x180014885  mov     edx, 11B1h; nIDDlgItem
0x18001488a  mov     [rsp+38h+lParam], 0; lParam
0x180014893  mov     r9d, 3; wParam
0x180014899  mov     r8d, 0C5h; Msg
0x18001489f  mov     rcx, rdi; hDlg
0x1800148a2  call    cs:__imp_SendDlgItemMessageW
0x1800148a8  xor     r9d, r9d; wParam
0x1800148ab  mov     [rsp+38h+lParam], 3E7h; lParam
0x1800148b4  mov     edx, 11B2h; nIDDlgItem
0x1800148b9  mov     r8d, 46Fh; Msg
0x1800148bf  mov     rcx, rdi; hDlg
0x1800148c2  call    cs:__imp_SendDlgItemMessageW
0x1800148c8  mov     rax, [rbx+238h]
0x1800148cf  xor     r9d, r9d; wParam
0x1800148d2  mov     edx, 11B2h; nIDDlgItem
0x1800148d7  mov     r8d, 471h; Msg
0x1800148dd  mov     ecx, [rax+10h]
0x1800148e0  mov     [rsp+38h+lParam], rcx; lParam
0x1800148e5  mov     rcx, rdi; hDlg
0x1800148e8  call    cs:__imp_SendDlgItemMessageW
0x1800148ee  mov     r8, [rbx+238h]
0x1800148f5  xor     r9d, r9d; bSigned
0x1800148f8  mov     edx, 11B1h; nIDDlgItem
0x1800148fd  mov     rcx, rdi; hDlg
0x180014900  mov     r8d, [r8+10h]; uValue
0x180014904  call    cs:__imp_SetDlgItemInt
0x18001490a  mov     rbx, [rsp+38h+arg_0]
0x18001490f  xor     eax, eax
0x180014911  add     rsp, 30h
0x180014915  pop     rdi
0x180014916  retn
```
