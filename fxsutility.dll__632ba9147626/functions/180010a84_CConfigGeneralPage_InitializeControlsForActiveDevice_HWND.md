# CConfigGeneralPage::InitializeControlsForActiveDevice(HWND__ *)

- ea: `0x180010a84`
- end: `0x180010bc1`
- name: `?InitializeControlsForActiveDevice@CConfigGeneralPage@@AEBAKPEAUHWND__@@@Z`
- size: `317`
- prototype: `unsigned int(CConfigGeneralPage *__hidden this, HWND)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x1800115b0`

## callees

- `0x1800107ac`
- `0x18001080c`
- `0x180010a84`

## import_xrefs

- `USER32!EnableWindow` at `0x180010ac5`
- `USER32!EnableWindow` at `0x180010ac5`
- `USER32!SetDlgItemTextW` at `0x180010aa0`
- `USER32!SetDlgItemTextW` at `0x180010aa0`
- `USER32!SendMessageW` at `0x180010b29`
- `USER32!SendMessageW` at `0x180010b53`
- `USER32!SendMessageW` at `0x180010b29`
- `USER32!SendMessageW` at `0x180010b53`
- `USER32!SetDlgItemInt` at `0x180010b3e`
- `USER32!SetDlgItemInt` at `0x180010b3e`
- `USER32!CheckDlgButton` at `0x180010ade`
- `USER32!CheckDlgButton` at `0x180010b6a`
- `USER32!CheckDlgButton` at `0x180010b81`
- `USER32!CheckDlgButton` at `0x180010b8e`
- `USER32!CheckDlgButton` at `0x180010ba4`
- `USER32!CheckDlgButton` at `0x180010ade`
- `USER32!CheckDlgButton` at `0x180010b6a`
- `USER32!CheckDlgButton` at `0x180010b81`
- `USER32!CheckDlgButton` at `0x180010b8e`
- `USER32!CheckDlgButton` at `0x180010ba4`
- `USER32!SendDlgItemMessageW` at `0x180010b01`
- `USER32!SendDlgItemMessageW` at `0x180010b01`
- `USER32!GetDlgItem` at `0x180010aba`
- `USER32!GetDlgItem` at `0x180010b0f`
- `USER32!GetDlgItem` at `0x180010aba`
- `USER32!GetDlgItem` at `0x180010b0f`

## pseudocode

```c
__int64 __fastcall CConfigGeneralPage::InitializeControlsForActiveDevice(CConfigGeneralPage *this, HWND a2)
{
  HWND DlgItem; // rax
  HWND v5; // rbx
  CConfigGeneralPage *v6; // rcx
  CConfigGeneralPage *v7; // rcx

  SetDlgItemTextW(a2, 4504, *((LPCWSTR *)this + 7));
  if ( *((_DWORD *)this + 10) == 1 )
  {
    DlgItem = GetDlgItem(a2, 4505);
    EnableWindow(DlgItem, 0);
  }
  CheckDlgButton(a2, 4506, *((_DWORD *)this + 22) != 0);
  SendDlgItemMessageW(a2, 4510, 0xC5u, 2u, 0);
  v5 = GetDlgItem(a2, 4511);
  SendMessageW(v5, 0x46Fu, 1u, 99);
  SetDlgItemInt(a2, 4510, *((_DWORD *)this + 25), 0);
  SendMessageW(v5, 0x471u, 0, *((unsigned int *)this + 25));
  if ( *((_DWORD *)this + 23) )
  {
    CheckDlgButton(a2, 4507, 1u);
    if ( *((_DWORD *)this + 23) == 2 )
    {
      CheckDlgButton(a2, 4508, 1u);
    }
    else
    {
      CheckDlgButton(a2, 4509, 1u);
      CConfigGeneralPage::EnableRingsAndSpinControls(v6, a2, 1);
    }
  }
  else
  {
    CheckDlgButton(a2, 4507, 0);
    CConfigGeneralPage::EnableReceiveControls(v7, a2, 0);
  }
  return 0;
}

```

## disassembly

```asm
0x180010a84  push    rbx
0x180010a86  push    rsi
0x180010a87  push    rdi
0x180010a88  push    r15
0x180010a8a  sub     rsp, 38h
0x180010a8e  mov     r8, [rcx+38h]; lpString
0x180010a92  mov     rdi, rdx
0x180010a95  mov     rsi, rcx
0x180010a98  mov     edx, 1198h; nIDDlgItem
0x180010a9d  mov     rcx, rdi; hDlg
0x180010aa0  call    cs:__imp_SetDlgItemTextW
0x180010aa6  mov     r15d, 1
0x180010aac  cmp     [rsi+28h], r15d
0x180010ab0  jnz     short loc_180010ACB
0x180010ab2  mov     edx, 1199h; nIDDlgItem
0x180010ab7  mov     rcx, rdi; hDlg
0x180010aba  call    cs:__imp_GetDlgItem
0x180010ac0  mov     rcx, rax; hWnd
0x180010ac3  xor     edx, edx; bEnable
0x180010ac5  call    cs:__imp_EnableWindow
0x180010acb  xor     r8d, r8d
0x180010ace  mov     edx, 119Ah; nIDButton
0x180010ad3  cmp     [rsi+58h], r8d
0x180010ad7  mov     rcx, rdi; hDlg
0x180010ada  setnz   r8b; uCheck
0x180010ade  call    cs:__imp_CheckDlgButton
0x180010ae4  mov     edx, 119Eh; nIDDlgItem
0x180010ae9  mov     [rsp+58h+lParam], 0; lParam
0x180010af2  mov     r9d, 2; wParam
0x180010af8  mov     r8d, 0C5h; Msg
0x180010afe  mov     rcx, rdi; hDlg
0x180010b01  call    cs:__imp_SendDlgItemMessageW
0x180010b07  mov     edx, 119Fh; nIDDlgItem
0x180010b0c  mov     rcx, rdi; hDlg
0x180010b0f  call    cs:__imp_GetDlgItem
0x180010b15  mov     r9d, 63h ; 'c'; lParam
0x180010b1b  mov     r8, r15; wParam
0x180010b1e  mov     rcx, rax; hWnd
0x180010b21  mov     edx, 46Fh; Msg
0x180010b26  mov     rbx, rax
0x180010b29  call    cs:__imp_SendMessageW
0x180010b2f  mov     r8d, [rsi+64h]; uValue
0x180010b33  xor     r9d, r9d; bSigned
0x180010b36  mov     edx, 119Eh; nIDDlgItem
0x180010b3b  mov     rcx, rdi; hDlg
0x180010b3e  call    cs:__imp_SetDlgItemInt
0x180010b44  mov     r9d, [rsi+64h]; lParam
0x180010b48  xor     r8d, r8d; wParam
0x180010b4b  mov     edx, 471h; Msg
0x180010b50  mov     rcx, rbx; hWnd
0x180010b53  call    cs:__imp_SendMessageW
0x180010b59  cmp     dword ptr [rsi+5Ch], 0
0x180010b5d  mov     edx, 119Bh; nIDButton
0x180010b62  mov     rcx, rdi; hDlg
0x180010b65  jz      short loc_180010BA1
0x180010b67  mov     r8d, r15d; uCheck
0x180010b6a  call    cs:__imp_CheckDlgButton
0x180010b70  cmp     dword ptr [rsi+5Ch], 2
0x180010b74  mov     r8d, r15d; uCheck
0x180010b77  mov     rcx, rdi; hDlg
0x180010b7a  jnz     short loc_180010B89
0x180010b7c  mov     edx, 119Ch; nIDButton
0x180010b81  call    cs:__imp_CheckDlgButton
0x180010b87  jmp     short loc_180010BB5
0x180010b89  mov     edx, 119Dh; nIDButton
0x180010b8e  call    cs:__imp_CheckDlgButton
0x180010b94  mov     r8d, r15d; int
0x180010b97  mov     rdx, rdi; HWND
0x180010b9a  call    ?EnableRingsAndSpinControls@CConfigGeneralPage@@AEBAKPEAUHWND__@@H@Z; CConfigGeneralPage::EnableRingsAndSpinControls(HWND__ *,int)
0x180010b9f  jmp     short loc_180010BB5
0x180010ba1  xor     r8d, r8d; uCheck
0x180010ba4  call    cs:__imp_CheckDlgButton
0x180010baa  xor     r8d, r8d; int
0x180010bad  mov     rdx, rdi; HWND
0x180010bb0  call    ?EnableReceiveControls@CConfigGeneralPage@@AEBAKPEAUHWND__@@H@Z; CConfigGeneralPage::EnableReceiveControls(HWND__ *,int)
0x180010bb5  xor     eax, eax
0x180010bb7  add     rsp, 38h
0x180010bbb  pop     r15
0x180010bbd  pop     rdi
0x180010bbe  pop     rsi
0x180010bbf  pop     rbx
0x180010bc0  retn
```
