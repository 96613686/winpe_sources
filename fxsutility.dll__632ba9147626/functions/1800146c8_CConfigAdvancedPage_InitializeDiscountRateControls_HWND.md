# CConfigAdvancedPage::InitializeDiscountRateControls(HWND__ *)

- ea: `0x1800146c8`
- end: `0x1800147ea`
- name: `?InitializeDiscountRateControls@CConfigAdvancedPage@@AEBAKPEAUHWND__@@@Z`
- size: `290`
- prototype: `unsigned int(CConfigAdvancedPage *__hidden this, HWND)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180014bc0`

## callees

- `0x180006724`
- `0x180015cf0`

## import_xrefs

- `KERNEL32!GetLocalTime` at `0x180014709`
- `KERNEL32!GetLocalTime` at `0x180014709`
- `USER32!SendDlgItemMessageW` at `0x18001472a`
- `USER32!SendDlgItemMessageW` at `0x180014764`
- `USER32!SendDlgItemMessageW` at `0x180014785`
- `USER32!SendDlgItemMessageW` at `0x1800147c1`
- `USER32!SendDlgItemMessageW` at `0x18001472a`
- `USER32!SendDlgItemMessageW` at `0x180014764`
- `USER32!SendDlgItemMessageW` at `0x180014785`
- `USER32!SendDlgItemMessageW` at `0x1800147c1`

## pseudocode

```c
__int64 __fastcall CConfigAdvancedPage::InitializeDiscountRateControls(CConfigAdvancedPage *this, HWND a2)
{
  __int64 v4; // rcx
  __int64 v5; // r9
  _SYSTEMTIME SystemTime; // [rsp+30h] [rbp-238h] BYREF
  unsigned __int16 lParam[264]; // [rsp+40h] [rbp-228h] BYREF

  SystemTime = 0;
  GetSecondsFreeTimeFormat(lParam);
  GetLocalTime(&SystemTime);
  SendDlgItemMessageW(a2, 4534, 0x1032u, 0, (LPARAM)lParam);
  v4 = *((_QWORD *)this + 71);
  SystemTime.wHour = *(_WORD *)(v4 + 20);
  SystemTime.wMinute = *(_WORD *)(v4 + 22);
  SendDlgItemMessageW(a2, 4534, 0x1002u, 0, (LPARAM)&SystemTime);
  SendDlgItemMessageW(a2, 4535, 0x1032u, 0, (LPARAM)lParam);
  v5 = *((_QWORD *)this + 71);
  SystemTime.wHour = *(_WORD *)(v5 + 24);
  SystemTime.wMinute = *(_WORD *)(v5 + 26);
  SendDlgItemMessageW(a2, 4535, 0x1002u, 0, (LPARAM)&SystemTime);
  return 0;
}

```

## disassembly

```asm
0x1800146c8  mov     [rsp+arg_10], rbx
0x1800146cd  push    rdi
0x1800146ce  sub     rsp, 260h
0x1800146d5  mov     rax, cs:__security_cookie
0x1800146dc  xor     rax, rsp
0x1800146df  mov     [rsp+268h+var_18], rax
0x1800146e7  mov     rdi, rdx
0x1800146ea  mov     rbx, rcx
0x1800146ed  xorps   xmm0, xmm0
0x1800146f0  lea     rcx, [rsp+268h+var_228]; unsigned __int16 *
0x1800146f5  mov     edx, 104h
0x1800146fa  movups  xmmword ptr [rsp+268h+SystemTime.wYear], xmm0
0x1800146ff  call    GetSecondsFreeTimeFormat
0x180014704  lea     rcx, [rsp+268h+SystemTime]; lpSystemTime
0x180014709  call    cs:__imp_GetLocalTime
0x18001470f  lea     rax, [rsp+268h+var_228]
0x180014714  xor     r9d, r9d; wParam
0x180014717  mov     edx, 11B6h; nIDDlgItem
0x18001471c  mov     [rsp+268h+lParam], rax; lParam
0x180014721  mov     r8d, 1032h; Msg
0x180014727  mov     rcx, rdi; hDlg
0x18001472a  call    cs:__imp_SendDlgItemMessageW
0x180014730  mov     rcx, [rbx+238h]
0x180014737  xor     r9d, r9d; wParam
0x18001473a  mov     edx, 11B6h; nIDDlgItem
0x18001473f  mov     r8d, 1002h; Msg
0x180014745  movzx   eax, word ptr [rcx+14h]
0x180014749  mov     [rsp+268h+SystemTime.wHour], ax
0x18001474e  movzx   eax, word ptr [rcx+16h]
0x180014752  mov     rcx, rdi; hDlg
0x180014755  mov     [rsp+268h+SystemTime.wMinute], ax
0x18001475a  lea     rax, [rsp+268h+SystemTime]
0x18001475f  mov     [rsp+268h+lParam], rax; lParam
0x180014764  call    cs:__imp_SendDlgItemMessageW
0x18001476a  lea     rax, [rsp+268h+var_228]
0x18001476f  xor     r9d, r9d; wParam
0x180014772  mov     edx, 11B7h; nIDDlgItem
0x180014777  mov     [rsp+268h+lParam], rax; lParam
0x18001477c  mov     r8d, 1032h; Msg
0x180014782  mov     rcx, rdi; hDlg
0x180014785  call    cs:__imp_SendDlgItemMessageW
0x18001478b  mov     r9, [rbx+238h]
0x180014792  mov     edx, 11B7h; nIDDlgItem
0x180014797  mov     r8d, 1002h; Msg
0x18001479d  mov     rcx, rdi; hDlg
0x1800147a0  movzx   eax, word ptr [r9+18h]
0x1800147a5  mov     [rsp+268h+SystemTime.wHour], ax
0x1800147aa  movzx   eax, word ptr [r9+1Ah]
0x1800147af  xor     r9d, r9d; wParam
0x1800147b2  mov     [rsp+268h+SystemTime.wMinute], ax
0x1800147b7  lea     rax, [rsp+268h+SystemTime]
0x1800147bc  mov     [rsp+268h+lParam], rax; lParam
0x1800147c1  call    cs:__imp_SendDlgItemMessageW
0x1800147c7  xor     eax, eax
0x1800147c9  mov     rcx, [rsp+268h+var_18]
0x1800147d1  xor     rcx, rsp; StackCookie
0x1800147d4  call    __security_check_cookie
0x1800147d9  mov     rbx, [rsp+268h+arg_10]
0x1800147e1  add     rsp, 260h
0x1800147e8  pop     rdi
0x1800147e9  retn
```
