# CFileOwnerDialog::OnOwnerListComplete(void)

- ea: `0x180014604`
- end: `0x180014724`
- name: `?OnOwnerListComplete@CFileOwnerDialog@@AEAAXXZ`
- size: `288`
- prototype: `void __fastcall(CFileOwnerDialog *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x1800131a0`

## callees

- `0x180012e94`
- `0x1800132b0`
- `0x18001387c`
- `0x180019d24`
- `0x180019ee0`

## import_xrefs

- `USER32!SetWindowTextW` at `0x180014645`
- `USER32!SetWindowTextW` at `0x180014645`
- `USER32!EnableWindow` at `0x1800146a4`
- `USER32!EnableWindow` at `0x1800146b0`
- `USER32!EnableWindow` at `0x1800146bc`
- `USER32!EnableWindow` at `0x1800146d6`
- `USER32!EnableWindow` at `0x1800146f0`
- `USER32!EnableWindow` at `0x18001470a`
- `USER32!EnableWindow` at `0x1800146a4`
- `USER32!EnableWindow` at `0x1800146b0`
- `USER32!EnableWindow` at `0x1800146bc`
- `USER32!EnableWindow` at `0x1800146d6`
- `USER32!EnableWindow` at `0x1800146f0`
- `USER32!EnableWindow` at `0x18001470a`
- `USER32!SendMessageW` at `0x180014688`
- `USER32!SendMessageW` at `0x180014688`
- `USER32!GetDlgItem` at `0x180014639`
- `USER32!GetDlgItem` at `0x1800146cb`
- `USER32!GetDlgItem` at `0x1800146e5`
- `USER32!GetDlgItem` at `0x1800146ff`
- `USER32!GetDlgItem` at `0x180014639`
- `USER32!GetDlgItem` at `0x1800146cb`
- `USER32!GetDlgItem` at `0x1800146e5`
- `USER32!GetDlgItem` at `0x1800146ff`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall CFileOwnerDialog::OnOwnerListComplete(CFileOwnerDialog *this)
{
  const WCHAR *v2; // rbx
  HWND DlgItem; // rax
  HWND v4; // rbx
  HWND v5; // rax
  HWND v6; // rax
  HWND v7; // rax
  _BYTE v8[8]; // [rsp+20h] [rbp-38h] BYREF
  const WCHAR **v9; // [rsp+28h] [rbp-30h]

  CString::CString((CString *)v8, *(HINSTANCE *)this, 40623, *((unsigned int *)this + 23));
  v2 = *v9;
  DlgItem = GetDlgItem(*((HWND *)this + 2), 1084);
  SetWindowTextW(DlgItem, v2);
  v4 = (HWND)*((_QWORD *)this + 3);
  CFileOwnerDialog::CreateListColumns((HINSTANCE *)this, v4, *((_DWORD *)this + 23) > 1);
  CFileOwnerDialog::FillListView(this, (CFileOwnerDialog *)((char *)this + 80), v4, -1);
  SendMessageW(v4, 0x1036u, 0, 32);
  CFileOwnerDialog::InitializeOwnerCombo(this, (CFileOwnerDialog *)((char *)this + 80), *((HWND *)this + 4));
  EnableWindow(*((HWND *)this + 3), 1);
  EnableWindow(*((HWND *)this + 4), 1);
  EnableWindow(*((HWND *)this + 5), 1);
  v5 = GetDlgItem(*((HWND *)this + 2), 1082);
  EnableWindow(v5, 1);
  v6 = GetDlgItem(*((HWND *)this + 2), 1096);
  EnableWindow(v6, 1);
  v7 = GetDlgItem(*((HWND *)this + 2), 1095);
  EnableWindow(v7, 1);
  CString::~CString((CString *)v8);
}

```

## disassembly

```asm
0x180014604  push    rbx
0x180014606  push    rbp
0x180014607  push    rsi
0x180014608  push    rdi
0x180014609  sub     rsp, 38h
0x18001460d  mov     rsi, rcx
0x180014610  mov     r9d, [rcx+5Ch]
0x180014614  mov     r8d, 9EAFh; int
0x18001461a  mov     rdx, [rcx]; HINSTANCE
0x18001461d  lea     rcx, [rsp+58h+var_38]; this
0x180014622  call    ??0CString@@QEAA@PEAUHINSTANCE__@@HZZ; CString::CString(HINSTANCE__ *,int,...)
0x180014627  nop
0x180014628  mov     rax, [rsp+58h+var_30]
0x18001462d  mov     rbx, [rax]
0x180014630  mov     edx, 43Ch; nIDDlgItem
0x180014635  mov     rcx, [rsi+10h]; hDlg
0x180014639  call    cs:__imp_GetDlgItem
0x18001463f  mov     rdx, rbx; lpString
0x180014642  mov     rcx, rax; hWnd
0x180014645  call    cs:__imp_SetWindowTextW
0x18001464b  mov     rbx, [rsi+18h]
0x18001464f  mov     ebp, 1
0x180014654  cmp     [rsi+5Ch], ebp
0x180014657  setnle  r8b; bool
0x18001465b  mov     rdx, rbx; HWND
0x18001465e  mov     rcx, rsi; this
0x180014661  call    ?CreateListColumns@CFileOwnerDialog@@AEAAXPEAUHWND__@@_N@Z; CFileOwnerDialog::CreateListColumns(HWND__ *,bool)
0x180014666  or      r9d, 0FFFFFFFFh; int
0x18001466a  mov     r8, rbx; HWND
0x18001466d  lea     rdx, [rsi+50h]; struct COwnerList *
0x180014671  mov     rcx, rsi; this
0x180014674  call    ?FillListView@CFileOwnerDialog@@AEAAXAEBVCOwnerList@@PEAUHWND__@@H@Z; CFileOwnerDialog::FillListView(COwnerList const &,HWND__ *,int)
0x180014679  lea     r9d, [rbp+1Fh]; lParam
0x18001467d  xor     r8d, r8d; wParam
0x180014680  mov     edx, 1036h; Msg
0x180014685  mov     rcx, rbx; hWnd
0x180014688  call    cs:__imp_SendMessageW
0x18001468e  mov     r8, [rsi+20h]; HWND
0x180014692  lea     rdx, [rsi+50h]; struct COwnerList *
0x180014696  mov     rcx, rsi; this
0x180014699  call    ?InitializeOwnerCombo@CFileOwnerDialog@@AEAAXAEBVCOwnerList@@PEAUHWND__@@@Z; CFileOwnerDialog::InitializeOwnerCombo(COwnerList const &,HWND__ *)
0x18001469e  mov     edx, ebp; bEnable
0x1800146a0  mov     rcx, [rsi+18h]; hWnd
0x1800146a4  call    cs:__imp_EnableWindow
0x1800146aa  mov     edx, ebp; bEnable
0x1800146ac  mov     rcx, [rsi+20h]; hWnd
0x1800146b0  call    cs:__imp_EnableWindow
0x1800146b6  mov     edx, ebp; bEnable
0x1800146b8  mov     rcx, [rsi+28h]; hWnd
0x1800146bc  call    cs:__imp_EnableWindow
0x1800146c2  mov     edx, 43Ah; nIDDlgItem
0x1800146c7  mov     rcx, [rsi+10h]; hDlg
0x1800146cb  call    cs:__imp_GetDlgItem
0x1800146d1  mov     rcx, rax; hWnd
0x1800146d4  mov     edx, ebp; bEnable
0x1800146d6  call    cs:__imp_EnableWindow
0x1800146dc  mov     edx, 448h; nIDDlgItem
0x1800146e1  mov     rcx, [rsi+10h]; hDlg
0x1800146e5  call    cs:__imp_GetDlgItem
0x1800146eb  mov     rcx, rax; hWnd
0x1800146ee  mov     edx, ebp; bEnable
0x1800146f0  call    cs:__imp_EnableWindow
0x1800146f6  mov     edx, 447h; nIDDlgItem
0x1800146fb  mov     rcx, [rsi+10h]; hDlg
0x1800146ff  call    cs:__imp_GetDlgItem
0x180014705  mov     rcx, rax; hWnd
0x180014708  mov     edx, ebp; bEnable
0x18001470a  call    cs:__imp_EnableWindow
0x180014710  nop
0x180014711  lea     rcx, [rsp+58h+var_38]; this
0x180014716  call    ??1CString@@UEAA@XZ; CString::~CString(void)
0x18001471b  add     rsp, 38h
0x18001471f  pop     rdi
0x180014720  pop     rsi
0x180014721  pop     rbp
0x180014722  pop     rbx
0x180014723  retn
```
