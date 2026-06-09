# CDlgAddPolicyServer::OnToggleActiveDirectory(uint,int,HWND__ *)

- ea: `0x180024e24`
- end: `0x180024f90`
- name: `?OnToggleActiveDirectory@CDlgAddPolicyServer@@AEAAXIHPEAUHWND__@@@Z`
- size: `364`
- prototype: `void __fastcall(CDlgAddPolicyServer *__hidden this, unsigned int, int, HWND)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180025fe0`

## callees

- `0x180014440`
- `0x180024e24`

## import_xrefs

- `USER32!SendMessageW` at `0x180024e53`
- `USER32!SendMessageW` at `0x180024e53`
- `USER32!SetWindowTextW` at `0x180024efc`
- `USER32!SetWindowTextW` at `0x180024f66`
- `USER32!SetWindowTextW` at `0x180024efc`
- `USER32!SetWindowTextW` at `0x180024f66`
- `USER32!SendDlgItemMessageW` at `0x180024e7c`
- `USER32!SendDlgItemMessageW` at `0x180024e7c`
- `USER32!EnableWindow` at `0x180024e9a`
- `USER32!EnableWindow` at `0x180024eb8`
- `USER32!EnableWindow` at `0x180024ed9`
- `USER32!EnableWindow` at `0x180024f22`
- `USER32!EnableWindow` at `0x180024f43`
- `USER32!EnableWindow` at `0x180024f84`
- `USER32!EnableWindow` at `0x180024e9a`
- `USER32!EnableWindow` at `0x180024eb8`
- `USER32!EnableWindow` at `0x180024ed9`
- `USER32!EnableWindow` at `0x180024f22`
- `USER32!EnableWindow` at `0x180024f43`
- `USER32!EnableWindow` at `0x180024f84`

## pseudocode

```c
void __fastcall CDlgAddPolicyServer::OnToggleActiveDirectory(
        CDlgAddPolicyServer *this,
        __int64 a2,
        __int64 a3,
        HWND a4)
{
  HWND *v4; // rbx
  HWND *DlgItem; // rax
  HWND *v6; // rax
  HWND *v7; // rax
  HWND *v8; // rax
  HWND *v9; // rax
  HWND *v10; // rax
  HWND *v11; // rax
  HWND *v12; // rax
  HWND *v13; // rax
  HWND v14; // [rsp+58h] [rbp+20h] BYREF

  v14 = a4;
  v4 = (HWND *)((char *)this + 8);
  DlgItem = (HWND *)ATL::CWindow::GetDlgItem((char *)this + 8, &v14, 1004);
  if ( (unsigned int)SendMessageW(*DlgItem, 0xF0u, 0, 0) == 1 )
  {
    SendDlgItemMessageW(*v4, 1007, 0x14Eu, 1u, 0);
    v6 = (HWND *)ATL::CWindow::GetDlgItem(v4, &v14, 1007);
    EnableWindow(*v6, 0);
    v7 = (HWND *)ATL::CWindow::GetDlgItem(v4, &v14, 1003);
    EnableWindow(*v7, 0);
    v8 = (HWND *)ATL::CWindow::GetDlgItem(v4, &v14, 1005);
    EnableWindow(*v8, 1);
    v9 = (HWND *)ATL::CWindow::GetDlgItem(v4, &v14, 1003);
    SetWindowTextW(*v9, L"LDAP:");
  }
  else
  {
    v10 = (HWND *)ATL::CWindow::GetDlgItem(v4, &v14, 1007);
    EnableWindow(*v10, 1);
    v11 = (HWND *)ATL::CWindow::GetDlgItem(v4, &v14, 1003);
    EnableWindow(*v11, 1);
    v12 = (HWND *)ATL::CWindow::GetDlgItem(v4, &v14, 1003);
    SetWindowTextW(*v12, &Src);
    v13 = (HWND *)ATL::CWindow::GetDlgItem(v4, &v14, 1005);
    EnableWindow(*v13, 0);
  }
}

```

## disassembly

```asm
0x180024e24  mov     [rsp+arg_18], r9
0x180024e29  push    rbx
0x180024e2a  sub     rsp, 30h
0x180024e2e  lea     rbx, [rcx+8]
0x180024e32  mov     r8d, 3ECh
0x180024e38  mov     rcx, rbx
0x180024e3b  lea     rdx, [rsp+38h+arg_18]
0x180024e40  call    ?GetDlgItem@CWindow@ATL@@QEBA?AV12@H@Z; ATL::CWindow::GetDlgItem(int)
0x180024e45  xor     r9d, r9d; lParam
0x180024e48  xor     r8d, r8d; wParam
0x180024e4b  mov     edx, 0F0h; Msg
0x180024e50  mov     rcx, [rax]; hWnd
0x180024e53  call    cs:__imp_SendMessageW
0x180024e59  cmp     eax, 1
0x180024e5c  jnz     loc_180024F07
0x180024e62  mov     rcx, [rbx]; hDlg
0x180024e65  mov     edx, 3EFh; nIDDlgItem
0x180024e6a  mov     r9d, eax; wParam
0x180024e6d  mov     [rsp+38h+lParam], 0; lParam
0x180024e76  mov     r8d, 14Eh; Msg
0x180024e7c  call    cs:__imp_SendDlgItemMessageW
0x180024e82  mov     r8d, 3EFh
0x180024e88  lea     rdx, [rsp+38h+arg_18]
0x180024e8d  mov     rcx, rbx
0x180024e90  call    ?GetDlgItem@CWindow@ATL@@QEBA?AV12@H@Z; ATL::CWindow::GetDlgItem(int)
0x180024e95  xor     edx, edx; bEnable
0x180024e97  mov     rcx, [rax]; hWnd
0x180024e9a  call    cs:__imp_EnableWindow
0x180024ea0  mov     r8d, 3EBh
0x180024ea6  lea     rdx, [rsp+38h+arg_18]
0x180024eab  mov     rcx, rbx
0x180024eae  call    ?GetDlgItem@CWindow@ATL@@QEBA?AV12@H@Z; ATL::CWindow::GetDlgItem(int)
0x180024eb3  xor     edx, edx; bEnable
0x180024eb5  mov     rcx, [rax]; hWnd
0x180024eb8  call    cs:__imp_EnableWindow
0x180024ebe  mov     r8d, 3EDh
0x180024ec4  lea     rdx, [rsp+38h+arg_18]
0x180024ec9  mov     rcx, rbx
0x180024ecc  call    ?GetDlgItem@CWindow@ATL@@QEBA?AV12@H@Z; ATL::CWindow::GetDlgItem(int)
0x180024ed1  mov     edx, 1; bEnable
0x180024ed6  mov     rcx, [rax]; hWnd
0x180024ed9  call    cs:__imp_EnableWindow
0x180024edf  mov     r8d, 3EBh
0x180024ee5  lea     rdx, [rsp+38h+arg_18]
0x180024eea  mov     rcx, rbx
0x180024eed  call    ?GetDlgItem@CWindow@ATL@@QEBA?AV12@H@Z; ATL::CWindow::GetDlgItem(int)
0x180024ef2  lea     rdx, aLdap; "LDAP:"
0x180024ef9  mov     rcx, [rax]; hWnd
0x180024efc  call    cs:__imp_SetWindowTextW
0x180024f02  jmp     loc_180024F8A
0x180024f07  mov     r8d, 3EFh
0x180024f0d  lea     rdx, [rsp+38h+arg_18]
0x180024f12  mov     rcx, rbx
0x180024f15  call    ?GetDlgItem@CWindow@ATL@@QEBA?AV12@H@Z; ATL::CWindow::GetDlgItem(int)
0x180024f1a  mov     edx, 1; bEnable
0x180024f1f  mov     rcx, [rax]; hWnd
0x180024f22  call    cs:__imp_EnableWindow
0x180024f28  mov     r8d, 3EBh
0x180024f2e  lea     rdx, [rsp+38h+arg_18]
0x180024f33  mov     rcx, rbx
0x180024f36  call    ?GetDlgItem@CWindow@ATL@@QEBA?AV12@H@Z; ATL::CWindow::GetDlgItem(int)
0x180024f3b  mov     edx, 1; bEnable
0x180024f40  mov     rcx, [rax]; hWnd
0x180024f43  call    cs:__imp_EnableWindow
0x180024f49  mov     r8d, 3EBh
0x180024f4f  lea     rdx, [rsp+38h+arg_18]
0x180024f54  mov     rcx, rbx
0x180024f57  call    ?GetDlgItem@CWindow@ATL@@QEBA?AV12@H@Z; ATL::CWindow::GetDlgItem(int)
0x180024f5c  lea     rdx, Src; lpString
0x180024f63  mov     rcx, [rax]; hWnd
0x180024f66  call    cs:__imp_SetWindowTextW
0x180024f6c  mov     r8d, 3EDh
0x180024f72  lea     rdx, [rsp+38h+arg_18]
0x180024f77  mov     rcx, rbx
0x180024f7a  call    ?GetDlgItem@CWindow@ATL@@QEBA?AV12@H@Z; ATL::CWindow::GetDlgItem(int)
0x180024f7f  xor     edx, edx; bEnable
0x180024f81  mov     rcx, [rax]; hWnd
0x180024f84  call    cs:__imp_EnableWindow
0x180024f8a  add     rsp, 30h
0x180024f8e  pop     rbx
0x180024f8f  retn
```
