# CBaseDlg::OnInitDialog(uint,unsigned __int64,__int64,int &)

- ea: `0x180016214`
- end: `0x1800163ad`
- name: `?OnInitDialog@CBaseDlg@@QEAA_JI_K_JAEAH@Z`
- size: `409`
- prototype: `__int64 __usercall@<rax>(CBaseDlg *__hidden this@<rcx>, unsigned int@<edx>, unsigned __int64@<r8>, __int64@<r9>, int *)`
- caller_count: `1`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x180012030`

## callees

- `0x180011650`
- `0x180012f38`
- `0x18001563c`
- `0x180015f24`
- `0x180016214`
- `0x180030e6e`
- `0x180030ea0`

## import_xrefs

- `USER32!SendMessageW` at `0x180016286`
- `USER32!SendMessageW` at `0x1800162fb`
- `USER32!SendMessageW` at `0x180016286`
- `USER32!SendMessageW` at `0x1800162fb`
- `USER32!GetDC` at `0x180016263`
- `USER32!GetDC` at `0x180016263`
- `USER32!GetSysColor` at `0x180016318`
- `USER32!GetSysColor` at `0x180016374`
- `USER32!GetSysColor` at `0x180016318`
- `USER32!GetSysColor` at `0x180016374`
- `GDI32!GetObjectW` at `0x1800162b1`
- `GDI32!GetObjectW` at `0x1800162b1`
- `GDI32!CreateFontIndirectW` at `0x1800162c8`
- `GDI32!CreateFontIndirectW` at `0x1800162c8`
- `GDI32!CreateSolidBrush` at `0x180016320`
- `GDI32!CreateSolidBrush` at `0x18001637c`
- `GDI32!CreateSolidBrush` at `0x180016320`
- `GDI32!CreateSolidBrush` at `0x18001637c`
- `UxTheme!GetThemeColor` at `0x18001635f`
- `UxTheme!GetThemeColor` at `0x18001635f`
- `UxTheme!IsThemeActive` at `0x180016242`
- `UxTheme!IsThemeActive` at `0x180016332`
- `UxTheme!IsThemeActive` at `0x180016242`
- `UxTheme!IsThemeActive` at `0x180016332`
- `UxTheme!OpenThemeData` at `0x180016256`
- `UxTheme!OpenThemeData` at `0x180016256`

## string_xrefs

- `0x18001624f`: `TASKDIALOG`

## pseudocode

```c
__int64 __fastcall CBaseDlg::OnInitDialog(CBaseDlg *this, __int64 a2, __int64 a3, __int64 a4, int *a5)
{
  HWND *v5; // rsi
  BOOL v7; // eax
  HWND v8; // rcx
  HTHEME v9; // rax
  HWND v10; // rcx
  HDC DC; // rax
  CBaseDlg *v12; // rcx
  HFONT SecurityFont; // rax
  void *v14; // rdi
  WPARAM v15; // rdi
  HWND *DlgItem; // rax
  COLORREF SysColor; // eax
  void *v18; // rcx
  COLORREF v19; // ecx
  __int64 result; // rax
  COLORREF pColor; // [rsp+30h] [rbp-A8h] BYREF
  _BYTE v22[8]; // [rsp+38h] [rbp-A0h] BYREF
  LOGFONTW pv; // [rsp+40h] [rbp-98h] BYREF

  v5 = (HWND *)((char *)this + 8);
  v7 = IsThemeActive();
  v8 = *v5;
  if ( v7 )
  {
    v9 = OpenThemeData(v8, L"TASKDIALOG");
    v10 = *v5;
    *((_QWORD *)this + 12) = v9;
    DC = GetDC(v10);
    if ( !DC )
      goto LABEL_8;
    SecurityFont = CBaseDlg::CreateSecurityFont(v12, *((void **)this + 12), DC);
    goto LABEL_7;
  }
  v14 = (void *)SendMessageW(v8, 0x31u, 0, 0);
  if ( v14 )
  {
    memset_0(&pv, 0, sizeof(pv));
    if ( GetObjectW(v14, 92, &pv) )
    {
      pv.lfWeight = 700;
      SecurityFont = CreateFontIndirectW(&pv);
LABEL_7:
      *((_QWORD *)this + 10) = SecurityFont;
    }
  }
LABEL_8:
  v15 = *((_QWORD *)this + 10);
  if ( v15 )
  {
    DlgItem = (HWND *)ATL::CWindow::GetDlgItem(v5, v22, 1600);
    SendMessageW(*DlgItem, 0x30u, v15, 0);
    CBaseDlg::AdjustTitlePosition(this);
  }
  *((_DWORD *)this + 22) = IsUIHighContrast(0);
  SysColor = GetSysColor(15);
  *((_QWORD *)this + 8) = CreateSolidBrush(SysColor);
  pColor = 0;
  if ( IsThemeActive() && (v18 = (void *)*((_QWORD *)this + 12)) != 0 && GetThemeColor(v18, 1, 0, 3802, &pColor) >= 0 )
    v19 = pColor;
  else
    v19 = GetSysColor(5);
  *((_QWORD *)this + 9) = CreateSolidBrush(v19);
  result = 1;
  *a5 = 0;
  return result;
}

```

## disassembly

```asm
0x180016214  push    rbx
0x180016216  push    rsi
0x180016217  push    rdi
0x180016218  push    r14
0x18001621a  sub     rsp, 0B8h
0x180016221  mov     rax, cs:__security_cookie
0x180016228  xor     rax, rsp
0x18001622b  mov     [rsp+0D8h+var_38], rax
0x180016233  mov     r14, [rsp+0D8h+arg_20]
0x18001623b  lea     rsi, [rcx+8]
0x18001623f  mov     rbx, rcx
0x180016242  call    cs:__imp_IsThemeActive
0x180016248  mov     rcx, [rsi]; hWnd
0x18001624b  test    eax, eax
0x18001624d  jz      short loc_18001627C
0x18001624f  lea     rdx, pszClassList; "TASKDIALOG"
0x180016256  call    cs:__imp_OpenThemeData
0x18001625c  mov     rcx, [rsi]; hWnd
0x18001625f  mov     [rbx+60h], rax
0x180016263  call    cs:__imp_GetDC
0x180016269  test    rax, rax
0x18001626c  jz      short loc_1800162D2
0x18001626e  mov     rdx, [rbx+60h]; void *
0x180016272  mov     r8, rax; HDC
0x180016275  call    ?CreateSecurityFont@CBaseDlg@@IEAAPEAUHFONT__@@PEAXPEAUHDC__@@HH@Z; CBaseDlg::CreateSecurityFont(void *,HDC__ *,int,int)
0x18001627a  jmp     short loc_1800162CE
0x18001627c  xor     r9d, r9d; lParam
0x18001627f  xor     r8d, r8d; wParam
0x180016282  lea     edx, [r9+31h]; Msg
0x180016286  call    cs:__imp_SendMessageW
0x18001628c  mov     rdi, rax
0x18001628f  test    rax, rax
0x180016292  jz      short loc_1800162D2
0x180016294  xor     edx, edx; Val
0x180016296  lea     rcx, [rsp+0D8h+pv]; void *
0x18001629b  lea     r8d, [rdx+5Ch]; Size
0x18001629f  call    memset_0
0x1800162a4  lea     r8, [rsp+0D8h+pv]; pv
0x1800162a9  mov     edx, 5Ch ; '\'; c
0x1800162ae  mov     rcx, rdi; h
0x1800162b1  call    cs:__imp_GetObjectW
0x1800162b7  test    eax, eax
0x1800162b9  jz      short loc_1800162D2
0x1800162bb  lea     rcx, [rsp+0D8h+pv]; lplf
0x1800162c0  mov     [rsp+0D8h+var_88], 2BCh
0x1800162c8  call    cs:__imp_CreateFontIndirectW
0x1800162ce  mov     [rbx+50h], rax
0x1800162d2  mov     rdi, [rbx+50h]
0x1800162d6  test    rdi, rdi
0x1800162d9  jz      short loc_180016309
0x1800162db  mov     r8d, 640h
0x1800162e1  lea     rdx, [rsp+0D8h+var_A0]
0x1800162e6  mov     rcx, rsi
0x1800162e9  call    ?GetDlgItem@CWindow@ATL@@QEBA?AV12@H@Z; ATL::CWindow::GetDlgItem(int)
0x1800162ee  xor     r9d, r9d; lParam
0x1800162f1  mov     r8, rdi; wParam
0x1800162f4  mov     rcx, [rax]; hWnd
0x1800162f7  lea     edx, [r9+30h]; Msg
0x1800162fb  call    cs:__imp_SendMessageW
0x180016301  mov     rcx, rbx; this
0x180016304  call    ?AdjustTitlePosition@CBaseDlg@@IEAAXXZ; CBaseDlg::AdjustTitlePosition(void)
0x180016309  xor     ecx, ecx; int *
0x18001630b  call    ?IsUIHighContrast@@YAHPEAH@Z; IsUIHighContrast(int *)
0x180016310  mov     ecx, 0Fh; nIndex
0x180016315  mov     [rbx+58h], eax
0x180016318  call    cs:__imp_GetSysColor
0x18001631e  mov     ecx, eax; color
0x180016320  call    cs:__imp_CreateSolidBrush
0x180016326  mov     [rbx+40h], rax
0x18001632a  mov     [rsp+0D8h+var_A8], 0
0x180016332  call    cs:__imp_IsThemeActive
0x180016338  mov     edi, 1
0x18001633d  test    eax, eax
0x18001633f  jz      short loc_18001636F
0x180016341  mov     rcx, [rbx+60h]; hTheme
0x180016345  test    rcx, rcx
0x180016348  jz      short loc_18001636F
0x18001634a  lea     rax, [rsp+0D8h+var_A8]
0x18001634f  mov     r9d, 0EDAh; iPropId
0x180016355  xor     r8d, r8d; iStateId
0x180016358  mov     [rsp+0D8h+pColor], rax; pColor
0x18001635d  mov     edx, edi; iPartId
0x18001635f  call    cs:__imp_GetThemeColor
0x180016365  test    eax, eax
0x180016367  js      short loc_18001636F
0x180016369  mov     ecx, [rsp+0D8h+var_A8]
0x18001636d  jmp     short loc_18001637C
0x18001636f  mov     ecx, 5; nIndex
0x180016374  call    cs:__imp_GetSysColor
0x18001637a  mov     ecx, eax; color
0x18001637c  call    cs:__imp_CreateSolidBrush
0x180016382  mov     [rbx+48h], rax
0x180016386  mov     rax, rdi
0x180016389  mov     dword ptr [r14], 0
0x180016390  mov     rcx, [rsp+0D8h+var_38]
0x180016398  xor     rcx, rsp; StackCookie
0x18001639b  call    __security_check_cookie
0x1800163a0  add     rsp, 0B8h
0x1800163a7  pop     r14
0x1800163a9  pop     rdi
0x1800163aa  pop     rsi
0x1800163ab  pop     rbx
0x1800163ac  retn
```
